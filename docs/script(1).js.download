/*====================
 Ratio js
=======================*/
window.addEventListener("load", () => {
  const bgImg = document.querySelectorAll(".bg-img");
  for (i = 0; i < bgImg.length; i++) {
    let bgImgEl = bgImg[i];
    /// Optional Class Add ///
    if (bgImgEl.classList.contains("bg-top")) {
      bgImgEl.parentNode.classList.add("b-top");
    } else if (bgImgEl.classList.contains("bg-bottom")) {
      bgImgEl.parentNode.classList.add("b-bottom");
    } else if (bgImgEl.classList.contains("bg-center")) {
      bgImgEl.parentNode.classList.add("b-center");
    } else if (bgImgEl.classList.contains("bg-left")) {
      bgImgEl.parentNode.classList.add("b-left");
    } else if (bgImgEl.classList.contains("bg-right")) {
      bgImgEl.parentNode.classList.add("b-right");
    }

    /// Lazyloader Class Add ///
    if (bgImgEl.classList.contains("blur-up")) {
      bgImgEl.parentNode.classList.add("blur-up", "lazyload");
    }

    /// Size Class Add ///
    if (bgImgEl.classList.contains("bg_size_content")) {
      bgImgEl.parentNode.classList.add("b_size_content");
    }

    /// Ratio Style ///
    bgImgEl.parentNode.classList.add("bg-size");
    const bgSrc = bgImgEl.src;
    bgImgEl.style.display = "none";
    bgImgEl.parentNode.setAttribute(
      "style",
      `
background-image: url(${bgSrc});
background-size:cover;
background-position: center;
background-repeat: no-repeat;
display: block;
`
    );
  }
});

/*====================
 tap to top js
=======================*/
const btn = document.querySelector(".scroll");

btn.addEventListener("click", function () {
  scroll(0, 200);
});

window.onscroll = function showHide() {
  if (
    document.body.scrollTop > 500 ||
    document.documentElement.scrollTop > 500
  ) {
    btn.style.transform = "scale(1)";
  } else {
    btn.style.transform = "scale(0)";
  }
};

function scroll(target, duration) {
  if (duration <= 0) {
    return;
  }
  let difference = target - document.documentElement.scrollTop;
  let speed = (difference / duration) * 10;
  setTimeout(function () {
    document.documentElement.scrollTop += speed;
    if (document.documentElement.scrollTop == target) {
      return;
    }
    scroll(target, duration - 10);
  }, 10);
}

/*====================
  sticky header js
=======================*/
window.onscroll = function () {
  var header = document.querySelector("header");
  if (window.pageYOffset > 100) {
    header.classList.add("sticky");
  } else {
    header.classList.remove("sticky");
  }
};

/*====================
  tooltip js
=======================*/
AOS.init({
  once: true
});
window.addEventListener('load', AOS.refresh);
const tooltipTriggerList = document.querySelectorAll('[data-bs-toggle="tooltip"]')
const tooltipList = [...tooltipTriggerList].map(tooltipTriggerEl => new bootstrap.Tooltip(tooltipTriggerEl))

/*====================
  scroll header js
=======================*/
// Get all sections that have an ID defined
const sections = document.querySelectorAll("section[id]");

// Add an event listener listening for scroll
window.addEventListener("scroll", navHighlighter);

function navHighlighter() {
  // Get current scroll position
  let scrollY = window.pageYOffset;

  // Loop through sections to get height, top, and ID values for each
  sections.forEach(current => {
    const sectionHeight = current.offsetHeight;
    const sectionTop = current.offsetTop - 0;
    const sectionId = current.getAttribute("id");

    // Select the corresponding navigation link(s)
    const navLinks = document.querySelectorAll('.nav-item a[href*="' + sectionId + '"]');

    // Add or remove the 'active' class based on scroll position
    if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
      navLinks.forEach(link => {
        link.classList.add("active");
      });
    } else {
      navLinks.forEach(link => {
        link.classList.remove("active");
      });
    }
  });
}