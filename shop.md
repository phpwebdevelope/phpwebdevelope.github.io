<!DOCTYPE html>
<html>
  <head>
  <link rel="stylesheet" href="/style.css">
	  <link rel="stylesheet" href="includes/agency.css">
	  <link rel="stylesheet" href="includes/bootstrap.min.css">
  </head>
<body>
  <!-- Navigation -->
    <nav class="navbar navbar-default navbar-fixed-top">
        <div class="container">
            <!-- Brand and toggle get grouped for better mobile display -->
            <div class="navbar-header page-scroll">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand page-scroll" href="https://www.houseoffennel.com">House Of Fennel</a>
            </div>

        </div>
        <!-- /.container-fluid -->
    </nav>

    <!-- Header -->
    <header>
        <div class="container">
            <div class="intro-text">
              <div class="intro-lead-in" style="color:red;"></div>
                <div class="intro-heading"></div>  		
                <a href="#team" class="page-scroll btn btn-xl">Shop</a>
            </div>
        </div>
    </header> 
    <!-- Item section -->
    <section id="team" class="bg-light-gray">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 text-center">
                    <h3 class="section-subheading text-muted">Washable and Reuseable, built with filter pocket</h3>								
                </div>
            </div>
            <div class="row">		    
                {% for member in site.people %}
                <div class="col-sm-4">
                    <div class="team-member">
                        <img src="img/team/{{ member.pic }}.png" class="img-responsive" alt="">   
                    </div>
                </div>
                {% endfor %} 
		    <!--paypal buy button start-->
		    <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
<input type="hidden" name="cmd" value="_s-xclick">
<input type="hidden" name="hosted_button_id" value="S6X2GSYCY3ELW">
<table>
<tr><td><input type="hidden" name="on0" value="Quantity">Quantity</td></tr><tr><td><select name="os0">
	<option value="12 for $10.99 ea">12 for $10.99 ea $131.88 USD</option>
	<option value="6 for $12.99 ea">6 for $12.99 ea $77.94 USD</option>
</select> </td></tr>
<tr><td><input type="hidden" name="on1" value="Colour">Colour</td></tr><tr><td><select name="os1">
	<option value="Assorted">Assorted </option>
	<option value="Solid">Solid </option>
	<option value="Print">Print </option>
</select> </td></tr>
</table>
<input type="hidden" name="currency_code" value="USD">
<input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_buynowCC_LG.gif" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
<img alt="" border="0" src="https://www.paypalobjects.com/en_US/i/scr/pixel.gif" width="1" height="1">
</form>

		    <!--paypal buy button end-->
		<!--paypal check out-->
		    <div id="paypal-button-container"></div>
<script src="https://www.paypal.com/sdk/js?client-id=sb&currency=USD" data-sdk-integration-source="button-factory"></script>
<script>
  paypal.Buttons({
      style: {
          shape: 'pill',
          color: 'blue',
          layout: 'vertical',
          label: 'pay',
          
      },
      createOrder: function(data, actions) {
          return actions.order.create({
              purchase_units: [{
                  amount: {
                      value: '1'
                  }
              }]
          });
      },
      onApprove: function(data, actions) {
          return actions.order.capture().then(function(details) {
              alert('Transaction completed by ' + details.payer.name.given_name + '!');
          });
      }
  }).render('#paypal-button-container');
</script>
		    <!--paypal check out-->     
            </div>         
        </div>
    </section>
    </body>
</html>
