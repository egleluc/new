Sveikos, tai sutvarkyta dalis, yra 24 ir 25 eilutės, tereikėjo ištrinti vieną select elementą, tad pasikeiskite ir pas save.
Nepamirškite prisidėti active klasės, su kuria nurodysite, koks bus style kai linkas yra aktyvus. 
Sėkmės <3
Šiaip visas kodas yra čia:
  
$(document).ready(function() {
  
    var scrollLink = $('.scroll-m');
    
    // Smooth scrolling
    scrollLink.click(function(e) {
      e.preventDefault();
      $('body,html').animate({
        scrollTop: $(this.hash).offset().top
      }, 1000 );
    });
    
    // Active link switching
    $(window).scroll(function() {
      var scrollbarLocation = $(this).scrollTop();
      
      scrollLink.each(function() {
        
        var sectionOffset = $(this.hash).offset().top - 20;
        
        if ( sectionOffset <= scrollbarLocation ) {
            
          $(this).addClass('active');
          $(this).siblings().removeClass('active');
        }
      })
      
    })
  
  
  })