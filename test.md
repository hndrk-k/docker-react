# Test documentation

## Section 2

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam accumsan arcu at placerat tempor. Maecenas sed nulla non enim tempus pharetra at a mi. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum eget pretium sem. Nulla porttitor lacus a finibus iaculis. Morbi fringilla nunc non purus aliquet, sed varius magna varius. In at neque nec sapien ullamcorper sollicitudin. Phasellus lobortis suscipit luctus. Etiam sagittis accumsan lectus, vel lacinia ex euismod at. Donec tempor risus vel ex ultricies sollicitudin. Praesent semper, nulla non fringilla molestie, lacus elit venenatis elit, in rutrum felis lacus ac tellus. Nunc vitae vestibulum nisi.

### Section 3

Aliquam ut diam auctor, pulvinar turpis et, ultrices mauris. In finibus metus nec eleifend tincidunt. Nam eu augue lorem. Cras ultricies feugiat augue, quis posuere justo lobortis in. Duis et tortor sagittis, posuere dolor id, dictum erat. Maecenas posuere sagittis dignissim. Aliquam ac leo augue. Phasellus quis nunc vel nisi vehicula interdum eget et nulla. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut eget ante ex. Aenean et enim arcu. Pellentesque sed lacus sagittis, sodales augue eu, convallis urna. Nunc tempor erat non nulla ultrices, vitae interdum tellus cursus. Nulla maximus lectus justo, ut viverra nulla auctor sit amet. In viverra nunc justo, id cursus lectus tincidunt a. 

## Some Code:

```javascript
 var runningTotal = 0;
    const human = document.getElementById('human');
    const AI = document.getElementById('AI');
    const runningTotalText = document.getElementById('runningTotalText');
    const first = document.getElementById('first')
    const message = document.getElementById('message');
    const choiceButtons = new Array(3);
 
    // An function to restart game in any time, should be called as a callback
    // from the WWW page, see above for an example.
    //
    function restart()
    {
      runningTotal = 0;
      runningTotalText.value = runningTotal;
      human.value = '';
      AI.value = '';
      for (let i = 1; i <= 3; i++)
      {
        let button = document.getElementById('choice' + i);
        button.disabled = false;
        choiceButtons[i] = button;
      }
      message.innerText = '';
      if (Math.random() > 0.5)
      {
        update(AI, ai());
        first.innerText = 'The first move is AI move.'
      }
      else
        first.innerText = 'The first move is human move.'
    }
 
    // This function update an (read-only for a user) two text boxes
    // as well as runningTotal. It should be called only once per a move/turn.
    //
    function update(textBox, n)
    {
      textBox.value = n;
      runningTotal = runningTotal + n;
      runningTotalText.value = runningTotal;
      for (let i = 1; i <= 3; i++)
        if (runningTotal + i > 21)
          choiceButtons[i].disabled = true;
    }
```
