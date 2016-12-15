`<cpol-image>` is a polymer image resizer. It convert input file to resized blob or base64 type image. It's usefull when you want to upload thumbnail to firebase or other backend.

### How to install:

    bower install --save cpol-image

### Simple example to use &lt;cpol-image&gt;:

    <template>
      <style>
        :host {
          display: block;
        };
      </style>
      ...
      <input id="ifile" type="file">
      <cpol-image output-data='{{result}}'></cpol-image>
      <paper-button on-tap='_exe'>Process</paper-button>
      <img src$='[[_computeBlob(hasil)]]'>
      ...
    </template>
    <script>
      Polymer({
        ...
        _exe: function() {
          this.$.coba.processImageFile(this.$.ifile.files);
        },
        ...
      });
    </script>


### Set scale or width and/or height as you want.
#### Scale become the highest priority to be executed.

#### You can set scale number to be executed

    <cpol-image output-data='{{result}}' scale='0.5'></cpol-image>


#### You can set maxWidth and/or maxHeight to be executed

    <cpol-image output-data='{{result}}' max-width='1024'></cpol-image>
    <cpol-image output-data='{{result}}' max-height='768'></cpol-image>
    <cpol-image output-data='{{result}}' max-width='1024' max-height='400'></cpol-image>


### You can change output type between 'blob' and 'base64'.
Don't forget to handle both type carefully or you got an error.

    <cpol-image output-data='{{result}}' output-type='base64' scale='0.5'></cpol-image>