---
# An instance of the Contact widget.
widget: contact

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 130

title: Contact Me
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  #Email form provider
  form:
    provider: netlify
    formspree:
      id:
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: true

  # Contact details (edit or remove options as required)
  # email:
  # phone:
  address:
    street: Burgsteige 11
    city: Tübingen
    region: DE
    postcode: "72070"
    country: Germany
    country_code: DE
  coordinates:
    latitude: '48.519433'
    longitude: '9.050234'
  appointment_url: ''
  contact_links:
    - icon: twitter
      icon_pack: fab
      name: DM Me
      link: 'https://twitter.com/ArmandoFalcucci'
    # - icon: video
    #   icon_pack: fas
    #   name: Zoom Me
    #   link: 'https://zoom.com'

design:
  columns: '2'
---
