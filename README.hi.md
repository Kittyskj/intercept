# INTERCEPT

<p align="center">
  <img src="https://img.shields.io/badge/python-3.9+-blue.svg" alt="Python 3.9+">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="MIT License">
  <img src="https://img.shields.io/badge/platform-macOS%20%7C%20Linux-lightgrey.svg" alt="Platform">
</p>

<p align="center">
  <strong>सिग्नल इंटेलिजेंस प्लेटफ़ॉर्म</strong><br>
  सिग्नल इंटेलिजेंस टूल्स के लिए वेब-आधारित फ्रंट-एंड।
</p>

<p align="center">
  <img src="static/images/screenshots/screenshot2.png" alt="स्क्रीनशॉट">
</p>

---

## INTERCEPT क्या है?

INTERCEPT सिग्नल इंटेलिजेंस टूल्स के लिए एकीकृत वेब इंटरफ़ेस प्रदान करता है:

- **पेजर डिकोडिंग** — rtl_fm + multimon-ng के साथ POCSAG/FLEX
- **433MHz सेंसर** — rtl_433 के माध्यम से वेदर स्टेशन, TPMS, IoT डिवाइस
- **विमान ट्रैकिंग** — dump1090 के ADS-B के साथ रीयल-टाइम मानचित्र
- **सैटेलाइट ट्रैकिंग** — TLE डेटा का उपयोग कर पास पूर्वानुमान
- **WiFi रिकॉन** — aircrack-ng के मॉनिटर मोड से स्कैनिंग
- **ब्लूटूथ स्कैनिंग** — डिवाइस खोज और ट्रैकर डिटेक्शन

---

## कम्युनिटी

<p align="center">
  <a href="https://discord.gg/z3g3NJMe">हमारे Discord से जुड़ें</a>
</p>

---

## क्विक स्टार्ट

```bash
git clone https://github.com/smittix/intercept.git
cd intercept
./setup.sh
sudo python3 intercept.py
```

ब्राउज़र में http://localhost:5050 खोलें।

> **नोट:** Python 3.9+ और बाहरी टूल्स आवश्यक हैं। देखें [Hardware & Installation](docs/HARDWARE.md)।

### प्रॉक्सी और सुरक्षा नियंत्रण

बाहरी अनुरोध (जैसे सैटेलाइट TLE अपडेट) मानक प्रॉक्सी पर्यावरण चर को पढ़ते हैं। ऐप चलाने से पहले इनमें से कोई भी सेट करें:

- `INTERCEPT_HTTP_PROXY` / `HTTP_PROXY`
- `INTERCEPT_HTTPS_PROXY` / `HTTPS_PROXY`
- `INTERCEPT_FTP_PROXY` / `FTP_PROXY`
- `INTERCEPT_SOCKS_PROXY` / `SOCKS_PROXY`

आप सैटेलाइट TLE अनुरोधों के लिए सुरक्षा सीमाएँ भी कॉन्फ़िगर कर सकते हैं:

- `INTERCEPT_TLE_ALLOWED_HOSTS` — कॉमा से अलग अनुमत होस्ट सूची (डिफ़ॉल्ट: CelesTrak डोमेन)
- `INTERCEPT_TLE_REQUEST_TIMEOUT` — अनुरोध टाइमआउट (सेकंड, डिफ़ॉल्ट: `10`)
- `INTERCEPT_TLE_MAX_RESPONSE_SIZE` — अधिकतम प्रतिक्रिया आकार (बाइट, डिफ़ॉल्ट: `1048576`)
- `INTERCEPT_TLE_USER_AGENT` — कस्टम User-Agent हेडर

प्रॉक्सी वेरिएबल के बड़े और छोटे दोनों अक्षर स्वीकार किए जाते हैं।

---

## आवश्यकताएँ

- **Python 3.9+**
- **SDR हार्डवेयर** — RTL-SDR (~$25), LimeSDR या HackRF
- **बाहरी टूल्स** — rtl-sdr, multimon-ng, rtl_433, dump1090, aircrack-ng

त्वरित इंस्टॉल (Ubuntu/Debian):
```bash
sudo apt install rtl-sdr multimon-ng rtl-433 dump1090-mutability aircrack-ng bluez
```

विस्तार से जानें [Hardware & Installation](docs/HARDWARE.md)।

---

## दस्तावेज़

| दस्तावेज़ | विवरण |
|-----------|--------|
| [Features](docs/FEATURES.md) | सभी सुविधाओं की सूची |
| [Usage Guide](docs/USAGE.md) | प्रत्येक मोड के विस्तृत निर्देश |
| [Troubleshooting](docs/TROUBLESHOOTING.md) | सामान्य समस्याओं के समाधान |
| [Hardware & Installation](docs/HARDWARE.md) | SDR हार्डवेयर और टूल इंस्टॉलेशन |

---

## विकास

यह प्रोजेक्ट AI के सहयोग से विकसित किया गया है। उद्देश्य है Software Defined Radio को सरल, एकीकृत इंटरफ़ेस के माध्यम से अधिक सुलभ बनाना।

योगदान और सुधार का स्वागत है।

---

## अस्वीकरण

**यह सॉफ़्टवेयर केवल शैक्षणिक उद्देश्यों के लिए है।**

- केवल उचित अनुमोदन के साथ उपयोग करें
- बिना सहमति संचार को इंटरसेप्ट करना अवैध हो सकता है
- WiFi/ब्लूटूथ हमलों के लिए स्पष्ट अनुमति आवश्यक है
- लागू कानूनों का पालन करना आपकी ज़िम्मेदारी है

---

## लाइसेंस

MIT लाइसेंस — देखें [LICENSE](LICENSE)

## लेखक

निर्माता **smittix** — [GitHub](https://github.com/smittix)

## आभार

[rtl-sdr](https://osmocom.org/projects/rtl-sdr/wiki) |
[multimon-ng](https://github.com/EliasOenal/multimon-ng) |
[rtl_433](https://github.com/merbanan/rtl_433) |
[dump1090](https://github.com/flightaware/dump1090) |
[aircrack-ng](https://www.aircrack-ng.org/) |
[Leaflet.js](https://leafletjs.com/) |
[Celestrak](https://celestrak.org/)
