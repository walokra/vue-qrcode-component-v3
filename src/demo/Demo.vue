<template>
  <article class="container-fluid bg-faded">

      <header class="row bg-success d-flex flex-column justify-content-center align-items-center py-5">
          <h1 class="text-center text-white mb-4"><strong>vue-qrcode-component-v3</strong></h1>
          <h4 class="text-center text-white mb-4">Create QR codes with a simple Vue component</h4>
          <span class="text-white"><a class="text-white" href="https://github.com/walokra/vue-qrcode-component-v3">View on Github</a></span>
      </header>

      <div id="app" class="container">
          <section class="row pt-5">
              <div class="col-12 col-md-6 mb-5">
                  <h2 class="font-weight-bold mb-4">
                      Installation
                  </h2>

                  <p>
                      Follow the <a href="https://github.com/walokra/vue-qrcode-component-v3#installation">Installation guide</a> before trying to reproduce any of the following examples.
                  </p>

                  <p>
                      Remember that you need a Vue instance so your components can be handled by Vue.
                  </p>
              </div>

              <div class="col-12 col-lg-6 mb-5">
                  <code class="d-block bg-inverse text-white rounded p-4">
                      <span class="text-warning">import</span> <var>Vue</var> <span class="text-warning">from</span> 'vue'
                      <br>
                      <span class="text-warning">import</span> <var>VueQRCodeComponent</var> <span class="text-warning">from</span> 'vue-qrcode-component-v3'
                      <br><br>

                      <span class="text-muted">// Register the Vue component</span>
                      <br>
                      <var>Vue</var>.component('qr-code', <var>VueQRCodeComponent</var>)
                      <br><br>

                      <span class="text-muted">// Create a Vue instance</span>
                      <br>
                      <span class="text-info">const</span> <var>app</var> = <span class="text-warning">new</span> <var>Vue</var>({
                          <var class="text-success">el</var>: '#app'
                      });
                  </code>
              </div>
          </section>

          <hr>

          <section class="row pt-5">
              <div class="col-12 col-lg-6 d-flex justify-content-center justify-content-lg-start mb-5">
                  <qr-code text="Hello World!"></qr-code>
              </div>

              <div class="col-12 col-lg-6 mb-5 flex-first">
                  <h2 class="font-weight-bold mb-4">Simple usage</h2>

                  <p>
                      Just set a value for the required <var>text</var> prop.
                  </p>

                  <code class="d-block bg-inverse text-white rounded p-4">
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Hello World!"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                  </code>
              </div>
          </section>

          <hr>

          <section class="row pt-5">
              <div class="col-12 col-lg-6 mb-5">
                  <h2 class="font-weight-bold mb-4">Dynamic value</h2>

                  <p>
                      You can use <code class="inline-code">v-bind:</code> or the <code class="inline-code">:</code> shorthand to use a variable as <var>text</var> prop.
                  </p>

                  <code class="d-block bg-inverse text-white rounded p-4 mb-3">
                      &lt;<span class="text-danger">input</span> <span class="text-warning">type</span>="text" <span class="text-warning">v-model</span>="<var>message</var>"&gt;
                      <br><br>

                      &lt;<span class="text-danger">qr-code</span> :<span class="text-warning">text</span>="<var>message</var>"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                  </code>

                  <p>
                      Since the <var>text</var> prop has a watcher, when the value of the variable changes the component will generate a QR code for the new value.
                  </p>
              </div>

              <div class="col-12 col-lg-6 mb-5 d-flex flex-column align-items-center align-items-lg-end">
                  <input class="form-control mb-3" type="text" v-model="message">
                  <qr-code :text="message"></qr-code>
              </div>
          </section>

          <hr>

          <section class="row pt-5">
              <div class="col-12 col-lg-6 mb-5 d-flex justify-content-between">
                  <qr-code text="Hello World!" :size="100" color="blue"></qr-code>
                  <qr-code text="Hello World!" :size="125" color="#e74c3c" bg-color="gold"></qr-code>
                  <qr-code text="Hello World!" :size="150" color="#34495e" bg-color="#2ecc71"></qr-code>
              </div>

              <div class="col-12 col-lg-6 mb-5 flex-first">
                  <h2 class="font-weight-bold mb-4">Colors and sizing</h2>

                  <p>
                      You can fix the QR code width and height with the <var>size</var> prop (default 256, works in pixels).
                  </p>

                  <p>
                      Colors can be changed using <var>color</var> (default #000) and <var>bg-color</var> (default #FFF) props.
                  </p>

                  <p>
                      <strong>NOTE:</strong> If you use a darker color in <var>bg-color</var> than in <var>color</var> some QR code readers could have problems to understand your QR code.
                  </p>
              </div>

              <div class="col-12 mb-5">
                  <code class="d-block bg-inverse text-white rounded p-4 mb-3">
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">:size</span>="100" <span class="text-warning">color</span>="blue"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                      <br>
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">:size</span>="125" <span class="text-warning">color</span>="#e74c3c" <span class="text-warning">bg-color</span>="gold"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                      <br>
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">:size</span>="150" <span class="text-warning">color</span>="#34495e" <span class="text-warning">bg-color</span>="#2ecc71"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                  </code>
              </div>

              <div class="col-12">
                  <h2 class="font-weight-bold mb-4">
                      Error Correction Level
                  </h2>
              </div>

              <div class="col-12 col-lg-6 mb-5">
                  <p>
                      You can use <code class="inline-code">v-bind:</code> or the <code class="inline-code">:</code> shorthand to use a variable as <var>text</var> prop.
                  </p>
                  <p>
                      Since the <var>text</var> prop has a watcher, when the value of the variable changes the component will generate a QR code for the new value.
                  </p>
              </div>

              <div class="col-12 col-lg-6 mb-5 flex-last">
                  <code class="d-block bg-inverse text-white rounded p-4 mb-3">
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">error-level</span>="L"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                      <br>
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">error-level</span>="M"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                      <br>
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">error-level</span>="Q"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                      <br>
                      &lt;<span class="text-danger">qr-code</span> <span class="text-warning">text</span>="Your text" <span class="text-warning">error-level</span>="H"&gt;&lt;/<span class="text-danger">qr-code</span>&gt;
                  </code>

              </div>

              <div class="col-12 mb-5 d-flex flex-wrap justify-content-between">
                  <qr-code class="mb-5" text="I have a Low error level correction!" :size="200" error-level="L"></qr-code>
                  <qr-code class="mb-5" text="I have a Low-Medium error level correction!" :size="200" error-level="M"></qr-code>
                  <qr-code class="mb-5" text="I have a Medium-High error level correction!" :size="200" error-level="Q"></qr-code>
                  <qr-code class="mb-5" text="I have a High error level correction!" :size="200" error-level="H"></qr-code>
              </div>
          </section>

      </div>

      <section class="row bg-success py-5 justify-content-center">
          forked from&nbsp;<a class="text-white" href="https://github.com/gerardreches/vue-qrcode-component">gerardreches/vue-qrcode-component</a>&nbsp;<span class="text-white">by</span>&nbsp;<a class="text-white font-weight-bold" href="https://gerardreches.com">Gerard Reches</a>&nbsp;and updated for Vue 3
      </section>
  </article>
</template>

<script>
import QRCode from '../QRCode.vue'

export default {
  name: 'demo',
  components: {
    'qr-code': QRCode,
  },
  data () {
    return {
      message: 'Change me! :D'
    }
  },
}

</script>
