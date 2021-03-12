---
title: Lets Talk
hide_title: false
sections:
  - type: form_section
    section_id: contact-form
    content: |
      ### Old School Cool

      Send me an email, <alexander@virtuallycreative.ca>

      Complete the contact form, it goes to the email above.

      ***

      ### General Location

      #### 43.706802, -79.398336

      Virtually(Creative) is a digital agency.
      We currently do not accept in-person appointments.
      ![profile-pic](/images/profile-pic.svg)
    form_id: contactForm
    form_action: /thank-you
    form_fields:
      - input_type: text
        name: name
        label: Name
        default_value: Your name
        is_required: true
      - input_type: text
        name: pronouns
        label: Preferred Pronoun?
        default_value: They/Them
        options: []
        is_required: false
        type: form_field
      - input_type: email
        name: email
        label: Email
        default_value: Your email address
        is_required: true
      - input_type: select
        name: subject
        label: What services are you looking for?
        default_value: Please select
        options:
          - Accessibility (AODA)
          - WordPress Plans
          - Digital Marketing & SEO
          - Maintenance & Upkeep
          - Other
      - input_type: textarea
        name: message
        label: Message
        default_value: Your message
      - input_type: checkbox
        name: consent
        label: >-
          I understand that this form is storing my submitted information so I
          can be contacted.
      - input_type: tel
        name: Contact Number
        label: phone-number
        default_value: 416-
        options: []
        is_required: false
        type: form_field
    submit_label: Sent it!
seo:
  title: Contact
  description: This is the contact page
  extra:
    - name: 'og:type'
      value: website
      keyName: property
    - name: 'og:title'
      value: Contact
      keyName: property
    - name: 'og:description'
      value: This is the contact page
      keyName: property
    - name: 'twitter:card'
      value: summary
    - name: 'twitter:title'
      value: Contact
    - name: 'twitter:description'
      value: This is the contact page
layout: advanced
---
