# JS Modal

This project demonstrates a simple modal implementation using JavaScript, HTML, and CSS.

## Features

- Open and close modal windows
- Smooth transition effects

## Demo

Check out the live demo [here](https://qyuzet.github.io/js-modal).

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/Qyuzet/js-modal.git
    ```
2. Navigate to the project directory:
    ```sh
    cd js-modal
    ```

## Usage

Open `index.html` in your preferred browser to view the modal functionality.

## JavaScript Snippet Explanation

Here’s a brief explanation of the JavaScript code used in this project:

### Select Elements
```javascript
const modal = document.querySelector('.modal');
const overlay = document.querySelector('.overlay');
const btnCloseModal = document.querySelector('.close-modal');
const btnsOpenModal = document.querySelectorAll('.show-modal');
```
- Selects the modal, overlay, close button, and all open buttons.

### Open Modal Function
```javascript
const openModal = function () {
  modal.classList.remove('hidden');
  overlay.classList.remove('hidden');
};
```
- Removes the 'hidden' class from the modal and overlay to display them.

### Close Modal Function
```javascript
const closeModal = function () {
  modal.classList.add('hidden');
  overlay.classList.add('hidden');
};
```
- Adds the 'hidden' class to the modal and overlay to hide them.

### Event Listeners for Open Buttons
```javascript
for (let i = 0; i < btnsOpenModal.length; i++)
  btnsOpenModal[i].addEventListener('click', openModal);
```
- Adds a click event listener to each open button to trigger the `openModal` function.

### Event Listeners for Close Button and Overlay
```javascript
btnCloseModal.addEventListener('click', closeModal);
overlay.addEventListener('click', closeModal);
```
- Adds click event listeners to the close button and overlay to trigger the `closeModal` function.

### Event Listener for Escape Key
```javascript
document.addEventListener('keydown', function (e) {
  if (e.key === 'Escape' && !modal.classList.contains('hidden')) {
    closeModal();
  }
});
```
- Adds a keydown event listener to the document to close the modal when the Escape key is pressed.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
