jquery.busybox
==============

“BUSYBOX”, a sipler and cooler Ajax-loader. jQuery plugin

busyBox is intended to display the HTML box(es) to be updated by an AJAX request as 'busy' while performing such request.

This plugin differs from others in the way it just put a transparent 'layer' over the involved boxes (this using a jQuery selector) instead of putting it over the entire body, in this way the user will specifically know which sections of the page are being updated.

Example of usage:

    var loading = $("#my_container").busyBox({
      spinner: '<img src="themes/gold/images/loading.gif" />'
    });

    $.ajax({
      url: "/my-url",
      success: function(data, textStatus, XMLHttpRequest){
         $("#my_container").html(data).fadeIn('fast');
      },
      complete: function complete(XMLHttpRequest, textStatus){
        loading.busyBox('close');
      }
    });

In images directory, you can find some 'spinners' to reuse.
