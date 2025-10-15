# Inbyggd-Frihet's TKey hackathon

**Saturday the 25th October,
Inbyggd-Frihet will organize a TKey hackathon at Assured's office in Gothenburg.**

The Tillitis TKey is an open-source software, and open-source hardware, USB security token made in Sweden.
It is capable of providing an extra layer of security for use cases such as cryptographic signing, (SSH, PAM, etc.) login, and random number generation.
For more information about the TKey see below.

The goal of this hackathon is to collaborate on improving the TKey software and to work on finding, and implementing, more use cases for the TKey.
This is not a competitive hackathon, instead our aim is to get started with, and to improve, the TKey together with others - have fun and share ideas.

If you already know something that you want to implement or test, you can include it with your registration.
At the start of the event, these ideas will be presented, and people may freely choose an idea that they find interesting, and collaborate on for the day.

Our friends from Tillitis will join the event, and are able to answer questions.

**Prerequisites:** \
Bring a laptop if you wish to partake in the hackathon.

**Schedule:** \
**12:00 - Doors open** \
**13:00** [TALK] - Introduction \
**13:10** [TALK] - Getting started with TKey and the emulator\
**13:30** [TALK] - Introduction round and presentation of hackathon ideas.\
**14:00** [HACK] - Join a group and start hacking\
**17:00** [FOOD] \
**18:00** [HACK] - Hacking\
**20:00** [TALK] - Present your achievements\
**21:00 - End of event**

**Location:** \
Assured AB \
Norra Allégatan 7, 413 30 Göteborg \
Top floor \
<https://www.openstreetmap.org/node/12787669002#map=19/57.700238/11.956451>

## Registration

**Register by sending an email to: <inbyggd-frihet@r0x.se>** \
**Or, use this form: <https://forms.gle/1J851XTAcp38trH89>**

40 spots: first come, first served

## Further reading

_The TKey is an open source security token created by the Mullvad spin-off [Tillitis AB](https://tillitis.se/)._
_Both its software and its hardware (schematics, PCB, and FPGA design) are [open source](https://github.com/tillitis/tillitis-key1)._
_The TKey was released in April of 2023 with a price tag of 880 SEK (incl. tax) [and available from the Tillitis store](https://shop.tillitis.se/products/tkey)._

_The TKey is a small device drawing less than 100mA. It provides a few basic functions (either in firmware or by the provided [apps](https://github.com/tillitis/tillitis-key1-apps) and [libs](https://github.com/tillitis/tkey-libs)) such as Ed25519 signing, key derivation, BLAKE2 hashing, and a good random number generator (TRNG)._
_It also has a sensor for user confirmation._
_With these features, the TKey can be used for various functionalities, such as authentication (signing, SSH login, passkey, etc.), serving as a root of trust (sign/encrypt), or as a source of entropy (TRNG/CSPRNG)._

_The firmware is locked down and user applications need to be loaded onto the TKey after each boot, as it keeps no user-state between power cycles._
_However, it has an internal Unique Device Secret (UDS) which can be used to derive keys that are persistent across reboots, in addition to verify that the device and application have not been modified since last boot._
_See [the Tillitis developer documentation](https://dev.tillitis.se) for more technical details._

_Tillitis provides a few applications, but it is also possible to write apps for the TKey using regular C (Tillitis provides a limited standard lib)._

[<img src="tillitis-tkey.avif" width="480" />](.)

_Source: <https://www.assured.se/posts/getting-started-tillitis-tkey-security-token#anyway-whats-a-tkey>_


### Links

- [TKey](https://www.tillitis.se/products/tkey/)
- [TKey developer handbook](https://dev.tillitis.se/intro/)
- [Tillitis shop](https://shop.tillitis.se/)
- [For Linux, introduction to app development and use cases](https://www.assured.se/posts/getting-started-tillitis-tkey-security-token)
- [For Windows, introduction to use cases](https://www.assured.se/posts/sign-git-commits-tillitis-tkey-security-token)
- [Inbyggd-Frihet Göteborg](https://inbyggd-frihet.org)
