{%- comment -%}
Sofle key layout comparison widget.
Embedding the svg is required to manipulate the svg elements with JavaScript.
If you edit the svg, you may need to manually remove an xml header.
The default checked state in the html corresponds to layer visibility in inkscape.
{%- endcomment -%}
<style>
  #compare_toggles {
    padding: 15px 0 0 15px;
  }
  #compare_toggles,
  svg#sofle_key_compare {
    color: #212121;
    background-color: white;
    width: 100%;
  }
  .toggle {
    display: inline-block;
    margin-right: 10px;
    border-bottom: 10px solid white;
  }
</style>
<nav id="compare_toggles">
  <div class="toggle" style="border-bottom-color: #DB2F49;">
    <input type="checkbox" id="sofle_v1" value="g2889" checked>
    <label for="sofle_v1">Sofle V1</label>
  </div>
  <div class="toggle" style="border-bottom-color: #FA6845;">
    <input type="checkbox" id="sofle_v2" value="g11231">
    <label for="sofle_v2">Sofle V2</label>
  </div>
  <div class="toggle" style="border-bottom-color: #FCA553;">
    <input type="checkbox" id="sofle_rgb" value="g19945">
    <label for="sofle_rgb">Sofle RGB</label>
  </div>
  <div class="toggle" style="border-bottom-color: #509E97;">
    <input type="checkbox" id="sofle_choc" value="g7365">
    <label for="sofle_choc">Sofle Choc</label>
  </div>
  <div class="toggle" style="border-bottom-color: #371A4F;">
    <input type="checkbox" id="sofle_pico" value="g51912" checked>
    <label for="sofle_pico">Sofle Pico</label>
  </div>
</nav>

<script>
  var checkboxes = document.querySelectorAll('input[type=checkbox]');
  checkboxes.forEach(function (checkbox) {
    checkbox.addEventListener('change', function () {
      var element = document.getElementById(this.value);
      if (this.checked) {
        element.style.display = 'block';
      } else {
        element.style.display = 'none';
      }
    });
  });
</script>

{% include comparison.svg %}