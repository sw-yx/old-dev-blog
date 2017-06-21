---
layout: post
date: 2017-06-20
categories: pup
title: Dont pass props by reference
tags: happy
---

I have been battling a particularly terrible bug with a nested react component for the past day and only just solved it. The problem essentially was that I had a component (A) that was nested in another component (B), and when I unmounted B (B1) and switched to another instance of B (B2) the values from A (that were valid in B1) were somehow persisting in B2.

The reason this was happening is that I was instantiating A by supplying props from B, and then within A I was modifying those props so it could be read back again by B. However this modified my defaultProps within B and _THOSE_ persisted when i switched from B1 to B2.

god damn.

---

3.00. my task now is to add deleting capability to the guestEditor.

---

3.15. guestEditor complete! for posterity here is the complete solution

```javascript
/* eslint-disable max-len, no-return-assign */

import React from 'react';
import { Button } from 'react-bootstrap';

class GuestEditor extends React.Component {
  constructor(props) {
    super(props);
    // jsonlog('GuestEditorthis',this)
    this.onChange = this.onChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
    this.state = { items: this.props.items, text: '' };
  }

  onChange(e) {
    this.setState({ text: e.target.value });
  }

  handleSubmit() {
    const newItem = this.state.items ? this.state.items : [];
    const text = this.state.text;
    newItem.push(text);
    const newText = '';
    this.setState({ items: newItem, text: newText });
  }
  handleDelete(item) {
    const newItem = this.state.items;
    newItem.splice(newItem.indexOf(item), 1);
    this.setState({ items: newItem });
  }
  render() {
    return (
      <div className="container">
        <div className="inside-box">
          <b>Featured guests:</b>
        </div>
        <ul>{this.state.items && this.state.items.map((item, i) => {
          return <li key={i}><span>{item}</span><Button onClick={() => this.handleDelete(item)}>x</Button></li>;
        })}
        </ul>
        <input
          type="text"
          onChange={this.onChange}
          name="addguest"
          value={this.state.text}
          placeholder="Add guest..."
        />
        <Button onClick={() => this.handleSubmit()}>Add</Button>
      </div>
    );
  }
}

export default GuestEditor;

```


my task now is to port the guests module to the segments module.

the subtask is to create a timepicker. the ones i have tried arent good so I will have to do it myself.

---

10.00. after a long break i am back at it again with renewed purpose after JR emailed me with 180+ user potential. this is potentially a thing. I am going to have to create my own timepicker.
