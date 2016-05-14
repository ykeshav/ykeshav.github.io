---
layout: page
title: Contact Me
subtitle: Reach out Me Here...!!!
---
<form action="https://formspree.io/y.keshav1877@gmail.com" method="POST" class="form" id="contact-form">
  <div class="row" style="margin-top: 30px;">
    <div class="col-xs-6">
      <input type="text" name="name" class="form-control input-lg" placeholder="Name" title="Name"
             style="margin-bottom: 15px;">
    </div>
    <div class="col-xs-6">
      <input type="email" name="_replyto" class="form-control input-lg" placeholder="Email" title="Email"
             style="margin-bottom: 15px;">
    </div>
  </div>
  <input type="hidden" name="_subject" value="New User Contacted From ykeshav.github.io">
  <textarea type="text" name="content" class="form-control input-lg" placeholder="Message" title="Message"
            required="required" rows="3" style="margin-bottom: 15px;"></textarea>
  <input type="text" name="_gotcha" style="display:none">
  <input type="hidden" name="_next" value="./contact?message=Your message was sent successfully, thanks!"/>
  <button type="submit" class="btn btn-lg btn-primary">Submit</button>
</form>