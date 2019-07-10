var loanimation = bodymovin.loadAnimation({
    container: document.getElementById('loader'), // Required
    path: '/lottie/load-circle.json', // Required
    renderer: 'svg', // Required
    loop: true, // Optional
    autoplay: false, // Optional
});

var loanimation2 = bodymovin.loadAnimation({
    container: document.getElementById('loader2'), // Required
    path: '/lottie/Rose.json', // Required
    renderer: 'svg', // Required
    loop: false, // Optional
    autoplay: false, // Optional
});

function animationLoad(){
    $('#loader').hide();
    loanimation2.play();
    $.when($('#loader').delay(1000).fadeIn('slow')).done(loanimation.play());
}

 animationLoad();

$(window).on('load', function () {
    $.when($('#preloader').delay(500).fadeOut('slow')).done(function () {
        $('body').css({'overflow':'visible'});
    })
});