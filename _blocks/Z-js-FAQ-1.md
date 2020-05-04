---
header-bar-link: Javascript
heading: FAQ
html_code_block: |

  ``` HTML
  <section class="padded">

    <h2 class="centered padded-1"> FAQs </h2>

    <!-- dl stands for description list, with a description heading and a description description -->
    <dl class="accordion light-bg padded-1">

      <dt><a href="">Panel 1</a></dt>
      <dd>Pellentesque fermentum dolor. Aliquam quam lectus, facilisis auctor, ultrices ut, elementum vulputate, nunc.</dd>

      <dt><a href="">Panel 2</a></dt>
      <dd>Donec nec justo eget felis facilisis fermentum. Aliquam porttitor mauris sit amet orci. Aenean dignissim pellentesque felis.</dd>

      <dt><a href="">Panel 3</a></dt>
      <dd>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus hendrerit. Pellentesque aliquet nibh nec urna. In nisi neque, aliquet vel, dapibus id, mattis vel, nisi. Sed pretium, ligula sollicitudin laoreet viverra, tortor libero sodales leo,
        eget blandit nunc tortor eu nibh. Nullam mollis. Ut justo. Suspendisse potenti.</dd>

      </dl>
    </section>
css_code_block: |

  .accordion dt a {
  padding: 0.25rem;
  margin: 0.25rem 0;
  display:block;
  color: #e67e22;
  position: relative;
  text-decoration: none;
  }
  .accordion dd {
  padding: 0.5rem;
  }

  /* Accordian Icon */
  .accordion dt a::after {
  position: absolute;
  top: 0;
  right: 0;
  display: block;
  width: 1rem;
  height: 1rem;
  line-height: 1;
  text-align: center;
  -webkit-transition: all .35s;
  -o-transition: all .35s;
  transition: all .35s;
  }

  .accordion dt a::after {
  content: "+";
  }
  .open::after {
  transform: rotateZ(45deg);
  }

js_code_block: |

  $(document).ready(function() {
    var allPanels = $('.accordion > dd').hide();

      $('.accordion > dt > a').click(function() {

        allPanels.slideUp();

        $(this).filter('.open').removeClass('open').addClass('closing')
        $('.accordion > dt > a').removeClass('open');
      $(this).not(".closing").addClass('open').parent().next().slideDown();
        $('.accordion > dt > a').removeClass('closing');

        return false;
      });
    });

---
