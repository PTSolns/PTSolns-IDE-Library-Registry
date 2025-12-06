# PTSolns IDE Library Registry List
The repository contains the list of libraries that can be installed from within the Library Manager of PTSolns IDE. There are over 8,500+ libraries available to be installed by users of PTSolns IDE.

## Adding a library to PTSolns IDE Library Manager
It is possible to add a third-party library to the PTSolns IDE Library Registry List. Doing so would add that library to be searchable and installable from the Library Manager of PTSolns IDE by any user of the software. This would add visibility and reach of the developers of the third-party libraries.

At this time we do not have an automated method for third-parties to add the libraries themselves. Therefore, we ask interested parties to [Contact Us](https://ptsolns.com/contact-us) and include the URL in the email.

## Requirements for third-party library to be added to the PTSolns IDE Registry List
- Must include library.properties with the following details
  - name: the name of the library. Library names must contain only basic letters (A-Z or a-z) and numbers (0-9), spaces ( ), underscores (_), dots (.) and dashes (-). They must start with a letter or number. They must contain at least one letter. Note that libraries with a name containing the word "PTSolns" will not be allowed.
  - version: version of the library. Version should be [semver](https://semver.org/) compliant.
  - author: name/nickname of the authors and their email addresses (not mandatory) separated by comma (,)
  - maintainer: name and email of the maintainer
  - sentence: a sentence explaining the purpose of the library
  - paragraph: a longer description of the library. The value of sentence will be prepended to this, so you should start by writing the second sentence here
  - category: (defaults to Uncategorized) allowed values:
    - Display
    - Communication
    - Signal Input/Output
    - Sensors
    - Device Control
    - Timing
    - Data Storage
    - Data Processing
    - Other
  - url: the URL of the library project, for a person to visit. For example, the library's GitHub page. This is used for the "More info" links in Library Manager
  - architectures: (defaults to *) a comma separated list of architectures supported by the library. If the library doesn’t contain architecture specific code use * to match all architectures. This field is used as one factor in determining priority when multiple libraries match an #include directive and to provide a warning message when the library is compiled for a board of an architecture that doesn't match any on the list.
  - Example:
    <blockquote>
    name=PTSolns_InterfaceShield<br>
    version=1.1.4<br>
    author=PTSolns<br>
    maintainer=PTSolns <contact@PTSolns.com><br>
    sentence=PTSolns library for Interface-Shield.<br>
    paragraph=Interface 1602 LCD, four programmable push buttons and four programmable LEDs to your project via I2C bus. Interface-Shield has LCD control, including PWM backlight capability and contrast setting.       Interrupt pin on D9 can be enabled for advanced users.<br>
    category=Device Control<br>
    url=https://github.com/PTSolns/PTSolns_InterfaceShield<br>
    includes=PTSolns_InterfaceShield.h<br>
    architectures=*<br>
    </blockquote>
- Must include keywords.txt with the following details.
  - A list of keywords for the library may be specified in a file named keywords.txt located in the root of the library folder. When a keyword of any installed library is used in a sketch the PTSolns IDE colours it.
  - An example keywords.txt file:
    <blockquote>
    Test    KEYWORD1<br>
    doSomething KEYWORD2<br>
    </blockquote>
    This example file would cause PTSolns IDE to highlight Test as a data type, and doSomething as a method or function.

A full example with the proper DIR setup is shown:
<blockquote>
PTSolns_InterfaceShield/<br>
PTSolns_InterfaceShield/library.properties<br>
PTSolns_InterfaceShield/src<br>
PTSolns_InterfaceShield/src/PTSolns_InterfaceShield.cpp<br>
PTSolns_InterfaceShield/src/PTSolns_InterfaceShield.h<br>
PTSolns_InterfaceShield/examples/<br>
PTSolns_InterfaceShield/examples/Buttons_and_LEDs.ino<br>
PTSolns_InterfaceShield/examples/Debouncing.ino
</blockquote>

The Library will be considered non-compliant for any of the followng reasons:
- Incomplete or missing files as outlined above.
- The library repository must not contain any .exe files.
- The library repository must not contain a .development file.
- The library repository must not contain any symlinks.
- The library repository must not contain any files detected as infected by our antivirus scan.
- The library repository must have a Git tag (or release) and must have been compliant with all the above requirements at the time of that tag.
- The library repository must be hosted on a major Git-hosting website like GitHub, BitBucket or GitLab (other hosting sites may be considered on request).

## Updates
To publish a new release after a library has been accepted to the Library Registry.
- Library must be compliant with the above requirements
- Update the version in the library's library.properties
- Tag the library's repository once more and push the new tag.
