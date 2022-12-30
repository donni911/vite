# Badger Modal
[![Check](https://github.com/roma-borsuk/badger-modal/actions/workflows/check.yml/badge.svg)](https://github.com/roma-borsuk/badger-modal/actions/workflows/check.yml)
[![Deploy to Pages](https://github.com/roma-borsuk/badger-modal/actions/workflows/pages.yml/badge.svg)](https://roma-borsuk.github.io/badger-modal)
[![npm version](https://badge.fury.io/js/badger-modal.svg)](https://badge.fury.io/js/badger-modal)

## Demo
It's on the [GitHub Pages](https://roma-borsuk.github.io/badger-modal).

## Installation

```bash
yarn add --dev badger-modal
# or
npm install --save-dev badger-modal
```

or you can manually download Badger Modal from [repository](https://github.com/roma-borsuk/badger-modal/archive/refs/heads/main.zip).

## How to use

Add modal html:
``` html
<button type="button" data-modal-target="#exampleModal">Open Example Modal</button>
<div class="bm-modal" id="exampleModal" tabindex="-1" aria-hidden="true" aria-labelledby="exampleModalTitle">
  <div class="bm-dialog">
    <div class="bm-content">
      <div class="bm-header">
        <button type="button" class="bm-close" data-modal-dismiss aria-label="Close">Close</button>
      </div>
      <div class="bm-body">
        <div class="bm-title" id="exampleModalTitle">Modal Title</div>
        <div class="bm-text">Modal Text</div>
        <div class="bm-btns">
          <button type="button" data-modal-dismiss>Close</button>
        </div>
      </div>
    </div>
  </div>
</div>
```

Use styles and scripts:
``` html
<link rel="stylesheet" href="dist/badger-modal.css">
<link rel="stylesheet" href="dist/badger-modal.js">
```

Or import via ES modules:
``` javascript
import BModal from 'badger-modal';
```

To initialise:
``` javascript
const toggleEls = document.querySelectorAll('[data-modal-target]');

toggleEls.forEach(el => {
  const modalTarget = el.dataset.modalTarget;
  const modalEl = document.querySelector(modalTarget);

  if (modalEl) {
    const modal = new BModal(modalEl);

    el.addEventListener('click', e => {
      e.preventDefault();
      modal.show();
    });
  }
});
```

## License
[MIT License](https://en.wikipedia.org/wiki/MIT_License)
