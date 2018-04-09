---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "ancc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc" or "ancc") ancc=Acenet+ComputeCanada
venue: "McCain, 2018, Dalhousie University"        # brief name of host site without address (e.g., "Euphoric State University")
address: "6135 University Ave, Halifax, Nova Scotia"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "Canada"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "44.637475,-63.589654"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use)
humandate: "May 14-15, 2018"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 4:30 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-05-14      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2018-05-15        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["<a href=\"http://www.ace-net.ca/about-us/team/team-bios/#chrisgeroux\">Chris Geroux</a>"]
helper: ["<a href=\"https://blogs.dal.ca/libraries/2016/07/profile-roger-gillis-copyright-and-digital-humanities-librarian/\">Roger Gillis</a>"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["chris.geroux@ace-net.ca"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

{% comment %}
<h4>This is the workshop template. Delete these lines and use it to customize your own website.
If you are running a self-organized workshop or have not put in a workshop request yet, please also fill in 
<a href="{{site.amy_site}}/submit">this workshop request form</a> to let us know about your workshop
and our administrator may contact you if we need any extra information.</h4>
{% endcomment %}

<h2 id="general">General Information</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}

<p>
This two day workshop will start with a quick overview of advanced research computing and how it can be leveraged by researchers in the humanities and social sciences.In particular, this workshop will be of interest to those who are working with or thinking of starting digital humanities projects.
</p>
<p>
One new aspect of advanced research computing is of particular interest to the humanities and social sciences, cloud computing. The cloud portion of the workshop begins by introducing cloud computing as a concept and the role it can play in your research, whether you need a persistently available computing environment for a web service, or more computing power than your laptop can offer for Big Data problems and anything in between. The first project we will cover is setting up a standard HTML based website in order to introduce all the basics of working in a cloud computing environment. We will then walk through using the command line and how it can be used to configure your cloud computing environment for your specific research projects. Mediawiki, Omeka, Joomla, Drupal, and WordPress are popular content management systems (CMS) that have almost identical deployment methods and so while we will choose one of these to introduce security topics such as data encryption and software updates it will be representative of all these deployments.
</p>

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
<p id="who">
  <strong>Who:</strong>
  The course is aimed at researchers and students in the humanities and social sciences at Dalhousie University.
In particular, this workshop will be of interest to those who are working with or thinking of starting digital humanities projects.
  <strong>
    You don't need to have any previous knowledge of the tools
    that will be presented at the workshop.
  </strong>
</p>

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

<p><em>Surveys</em></p>
<p>Please be sure to complete this <a href="https://docs.google.com/forms/d/e/1FAIpQLSeCRI0ed5bZ0d8nu7fo1M9Wvcb5RkzukrjhXp2PNjzPxUeDvg/viewform?usp=sf_link">survey</a> after the workshop.</p>

<div class="row">
  <div class="col-md-6">
    <h3>Monday, May 14<sup>th</sup></h3>
    <table class="table table-striped">
      <tr> <td>09:00</td>  <td><a href="https://cgeroux.github.io/DH-cloud-course/reference/">Cloud Powering DH Research</a></td> </tr>
      <tr> <td>10:30</td>  <td>Coffee</td> </tr>
      <tr> <td>12:00</td>  <td>Lunch break</td> </tr>
      <tr> <td>13:00</td>  <td><a href="https://cgeroux.github.io/DH-cloud-course/reference/">Cloud Powering DH Research</a></td> </tr>
      <tr> <td>14:30</td>  <td>Coffee</td> </tr>
      <tr> <td>16:00</td>  <td>Wrap-up</td> </tr>
      <tr> <td>16:30</td>  <td>END</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Tuesday, May 15<sup>th</sup></h3>
    <table class="table table-striped">
      <tr> <td>09:00</td>  <td><a href="https://cgeroux.github.io/DH-cloud-course/">Cloud Powering DH Research</a> cont.</td> </tr>
      <tr> <td>10:30</td>  <td>Coffee</td> </tr>
      <tr> <td>12:00</td>  <td>Lunch break</td> </tr>
      <tr> <td>13:00</td>  <td><a href="https://cgeroux.github.io/DH-cloud-course/">Cloud Powering DH Research</a> cont.</td> </tr>
      <tr> <td>14:30</td>  <td>Coffee</td> </tr>
      <tr> <td>16:00</td>  <td>Wrap-up</td> </tr>
      <tr> <td>16:30</td>  <td>END</td> </tr>
    </table>
  </div>
</div>

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

<h2 id="syllabus">Syllabus</h2>
<div class="row">
    <h3 id="syllabus-python">Cloud Powering DH Research</h3>
    <ul>
      <li>Introduction to cloud computing</li>
      <li>Creating a virtual machine</li>
      <li>Applying updates</li>
      <li>Creating a web server</li>
      <li>Creating a Self-Signed SSL Certificate</li>
      <li>Creating a WordPress site</li>
      <li>Demo using Heat to create a mediawiki site</li>
      <li><a href="https://cgeroux.github.io/DH-cloud-course/reference/">Reference...</a></li>
    </ul>
  </div>

<hr/>

<h2 id="setup">Setup</h2>

<p>
  To participate in a this workshop, you will need access to the software and accounts described below. In addition, you will need an up-to-date web browser.
</p>

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell</h3>
  <p>
    Bash is a commonly-used shell that gives you the power to do simple tasks more quickly. Having access to the Bash shell on your laptop is a critical requirement for the cloud workshop. Without it you will not be able to follow along with the instructor for much of the workshop or participate in many of the hands on exercises. We will use the Bash shell to connect to our cloud virtual machines and interact with them.
  </p>
  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <a href="https://mobaxterm.mobatek.net/download.html">Download MobaXterm</a>, install, and verify it runs. This <a href="https://www.youtube.com/watch?v=yVI87WyBBfU">youtube</a> video demonstrates downloading and installing MobaXterm and how it is used to connect to a remote machine.
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        The default shell in all versions of macOS is Bash, so no need to install anything.  You access Bash from the Terminal (found in <code>/Applications/Utilities</code>). You may want to keep Terminal in your dock for this workshop.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        The default shell is usually Bash, but if your machine is set up differently you can run it by opening a terminal and typing <code>bash</code>.  There is no need to install anything.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}
<div id="account">
  <h3>Compute Canada Cloud Account</h3>
    <p>
      Having a Compute Canada cloud account will be helpful the workshop and while it isn't essential for the cloud workshop, it will allow you to keep your work and continue to have access to the cloud environment afterwards. If you are unable to get a Compute Canada cloud account for whatever reason, a guest account in a shared project will be provided for you to use for the duration of the workshop.
    </p>
    <p>
      Getting an account usually takes a few business days as there are humans involved in the process. Ensuring you have a Compute Canada Cloud account at least a week before the course begins is recommended. There are two steps to getting a CC Cloud account:
      <ol>
        <li>Get a Compute Canada account</li>
        <li>Get a Compute Canada <b>cloud</b> account</li>
      </ol>
      To get a Compute Canada account you need to be either a faculty member or a librarian at a recognized academic institution in Canada or have your account sponsored by someone who is. To get a Compute Canada account follow the instructions provided on this <a href="https://www.computecanada.ca/research-portal/account-management/apply-for-an-account/">Compute Canada page</a>. Once you have a CC account, you then apply for a cloud account <a href="https://www.computecanada.ca/research-portal/national-services/compute-canada-cloud/create-a-cloud-account/">here</a>. When applying for your cloud account you will need to provide your CC account user name and an email associated with your CC account.
    </p>
    <p>
      If you have any questions about getting a Compute Canada account or a Compute Canada cloud account please don't hesitate to contact the organizers of the workshop.
    </p>
</div>

