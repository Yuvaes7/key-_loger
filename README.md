# node-keylogger

Simple Node.js Linux-only keylogger using event emitters.

This project is inspired by [node-keyboard](https://github.com/Bornholm/node-keyboard). It has been rewritten to be as simple as possible without requiring any external modules and using `fs.createReadStream` instead of `fs.open`.

## Installation

To install the node-keylogger package, follow these steps:

1. Clone the repository:

    ```sh
    git clone https://github.com/Yuvaes7/key-_loger.git
    cd key-_loger
    ```

2. Install the dependencies:

    ```sh
    npm install
    ```

## Usage

Here is an example of how to use the keylogger in your Node.js project:

1. Create a `test.js` file in the root directory:

    ```sh
    touch test.js
    ```

2. Add the following code to `test.js`:

    ```javascript
    const Keyboard = require('./lib/index');

    const k = new Keyboard('event0'); // Replace 'event0' with the appropriate input event file for your keyboard
    k.on('keyup', console.log);
    k.on('keydown', console.log);
    k.on('keypress', console.log);
    k.on('error', console.error);
    ```

3. Run the test file with elevated permissions (as needed to access `/dev/input` devices):

    ```sh
    sudo node test.js
    ```

## Compilation

The project uses Babel to compile the ES6 code to ES5. To compile the code, run:

```sh
npm run compile
```

## Events

The keylogger emits the following events with the given data structure:

```javascript
{ 
  timeS: 1347572085, // Timestamp (Seconds part)
  timeMS: 741381, // Timestamp (Microseconds part)
  keyCode: 17, // Keyboard code
  keyId: 'KEY_W', // Key ID (Qwerty layout)
  type: 'keypress', // Event type
  dev: 'event2'  // Device
}
```

## TODO

- Add support for Windows
- Add support for OSX

## License

ISC
```

Feel free to copy and paste this content into your `README.md` file in your GitHub repository. 
