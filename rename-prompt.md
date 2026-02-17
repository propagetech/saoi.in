You are a naming assistant. Given a list of file paths and minimal context from a static website, suggest a new filename (basename only, same extension) for each file. Rules:
- Lowercase, kebab-case, no spaces. SEO-friendly and human-readable.
- For HTML: use page purpose (e.g. about-us.html, contact.html). Keep index.html as index.html.
- For CSS/JS: use purpose (e.g. main-styles.css, analytics.js).
- For images: use content (e.g. logo-infygate.webp, hero-banner.webp). Use alt/title when provided.
- Return a JSON object: keys = exact original path strings, values = new basename only (e.g. "main.css"). Preserve extension.
- Do not change path prefix (e.g. css/ stays css/ by returning "name.css" not "css/name.css").

Files and context:
[
  {
    "path": "404.html",
    "context": {
      "title": "",
      "first_heading": "404"
    }
  },
  {
    "path": "Members-of-SAI.html",
    "context": {
      "title": "Members Of SAI | Silk Association Of India",
      "first_heading": "MEMBERS OF SAI"
    }
  },
  {
    "path": "Sub-Committee-CRCs.html",
    "context": {
      "title": "Sub Committee Members - CRC's | Silk Association Of India",
      "first_heading": "SUB COMMITTEE MEMBERS\u00a0- CRC's"
    }
  },
  {
    "path": "Sub-Committee-RSPs.html",
    "context": {
      "title": "Sub Committee Members - RSP's | Silk Association Of India",
      "first_heading": "SUB COMMITTEE MEMBERS - RSP's"
    }
  },
  {
    "path": "Zonal-Chapter-1.html",
    "context": {
      "title": "Zonal Chapter - 02 | SAOI | Silk Association Of India",
      "first_heading": "Committee Members of Zonal Chapter - 1(Bengaluru Rual, Bengaluru Urban, Kolar, Chikkaballapur and Ramanagara)"
    }
  },
  {
    "path": "Zonal-Chapter_02.html",
    "context": {
      "title": "Zonal Chapter - 02 | SAOI",
      "first_heading": "Committee Members of Zonal Chapter - 02(Mandya, Mysore, Hassan)"
    }
  },
  {
    "path": "activities.html",
    "context": {
      "title": "Activities | Silk Association Of India",
      "first_heading": "ACTIVITIES"
    }
  },
  {
    "path": "blog_------------------------------------------------------------------------------------------source-from-daily-hunt.html",
    "context": {
      "title": "\u0cae\u0cb2\u0ccd\u0cac\u0cc6\u0cb0\u0cbf \u0cae\u0cbe\u0ca8\u0cb5 \u0ca6\u0cc7\u0cb9\u0ca6 \u0c95\u0cbe\u0cb5\u0cb2\u0cc1\u0c97\u0cbe\u0cb0\u0ca8\u0ca8\u0ccd\u0ca8\u0cc1 \u0cb0\u0c95\u0ccd\u0cb7\u0cbf\u0cb8\u0cc1\u0ca4\u0ccd\u0ca4\u0ca6\u0cc6, \u0ca6\u0cc7\u0cb9\u0c95\u0ccd\u0c95\u0cc6 \u0c95\u0cb0\u0ccb\u0ca8\u0cbe \u0caa\u0ccd\u0cb0\u0cb5\u0cc7\u0cb6\u0cbf\u0cb8\u0cc1\u0cb5\u0cc1\u0ca6\u0ca8\u0ccd\u0ca8\u0cc1 \u0ca4\u0ca1\u0cc6\u0caf\u0cc1\u0ca4\u0ccd\u0ca4\u0ca6\u0cc6 | Source From Daily Hunt",
      "first_heading": "\u0cae\u0cb2\u0ccd\u0cac\u0cc6\u0cb0\u0cbf \u0cae\u0cbe\u0ca8\u0cb5 \u0ca6\u0cc7\u0cb9\u0ca6 \u0c95\u0cbe\u0cb5\u0cb2\u0cc1\u0c97\u0cbe\u0cb0\u0ca8\u0ca8\u0ccd\u0ca8\u0cc1 \u0cb0\u0c95\u0ccd\u0cb7\u0cbf\u0cb8\u0cc1\u0ca4\u0ccd\u0ca4\u0ca6\u0cc6, \u0ca6\u0cc7\u0cb9\u0c95\u0ccd\u0c95\u0cc6 \u0c95\u0cb0\u0ccb\u0ca8\u0cbe \u0caa\u0ccd\u0cb0\u0cb5\u0cc7\u0cb6\u0cbf\u0cb8\u0cc1\u0cb5\u0cc1\u0ca6\u0ca8\u0ccd\u0ca8\u0cc1 \u0ca4\u0ca1\u0cc6\u0caf\u0cc1\u0ca4\u0ccd\u0ca4\u0ca6\u0cc6 | Source From Daily Hunt"
    }
  },
  {
    "path": "blog_--------------------------------------------------------------------------.html",
    "context": {
      "title": "\u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6\u0c97\u0cc2\u0ca1\u0cbf\u0ca8 \u0cac\u0cc6\u0cb2\u0cc6 \u0ca6\u0cbf\u0ca1\u0cc0\u0cb0\u0ccd \u0c8f\u0cb0\u0cbf\u0c95\u0cc6: \u0c95\u0cc6\u0c9c\u0cbf \u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6 \u0c97\u0cc2\u0ca1\u0cbf\u0c97\u0cc6 \u0c8e\u0cb7\u0ccd\u0c9f\u0cbf\u0ca6\u0cc6 \u0ca6\u0cb0? \u0c87\u0cb2\u0ccd\u0cb2\u0cbf\u0ca6\u0cc6 \u0cb5\u0cbf\u0cb5\u0cb0",
      "first_heading": "\u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6\u0c97\u0cc2\u0ca1\u0cbf\u0ca8 \u0cac\u0cc6\u0cb2\u0cc6 \u0ca6\u0cbf\u0ca1\u0cc0\u0cb0\u0ccd \u0c8f\u0cb0\u0cbf\u0c95\u0cc6: \u0c95\u0cc6\u0c9c\u0cbf \u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6 \u0c97\u0cc2\u0ca1\u0cbf\u0c97\u0cc6 \u0c8e\u0cb7\u0ccd\u0c9f\u0cbf\u0ca6\u0cc6 \u0ca6\u0cb0? \u0c87\u0cb2\u0ccd\u0cb2\u0cbf\u0ca6\u0cc6 \u0cb5\u0cbf\u0cb5\u0cb0"
    }
  },
  {
    "path": "blog_-----------------------------------------------.html",
    "context": {
      "title": "\u0cb0\u0cbe\u0c9c\u0ccd\u0caf\u0ca6\u0cb2\u0ccd\u0cb2\u0cc7 \u0cae\u0cca\u0ca6\u0cb2 \u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6 \u0c95\u0cc3\u0cb7\u0cbf \u0cae\u0cc6\u0c97\u0cbe \u0c95\u0ccd\u0cb2\u0cb8\u0ccd\u0c9f\u0cb0\u0ccd\u200c \u0cb0\u0c9a\u0ca8\u0cc6",
      "first_heading": "\u0cb0\u0cbe\u0c9c\u0ccd\u0caf\u0ca6\u0cb2\u0ccd\u0cb2\u0cc7 \u0cae\u0cca\u0ca6\u0cb2 \u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6 \u0c95\u0cc3\u0cb7\u0cbf \u0cae\u0cc6\u0c97\u0cbe \u0c95\u0ccd\u0cb2\u0cb8\u0ccd\u0c9f\u0cb0\u0ccd\u200c \u0cb0\u0c9a\u0ca8\u0cc6"
    }
  },
  {
    "path": "blog_--------------------------------.html",
    "context": {
      "title": "\u0c9a\u0cc0\u0ca8 \u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6\u0c97\u0cc6 \u0c95\u0ca1\u0cbf\u0cb5\u0cbe\u0ca3, \u0cb0\u0cc8\u0ca4\u0cb0\u0cbf\u0c97\u0cc6 \u0cb5\u0cb0?",
      "first_heading": "\u0c9a\u0cc0\u0ca8 \u0cb0\u0cc7\u0cb7\u0ccd\u0cae\u0cc6\u0c97\u0cc6 \u0c95\u0ca1\u0cbf\u0cb5\u0cbe\u0ca3, \u0cb0\u0cc8\u0ca4\u0cb0\u0cbf\u0c97\u0cc6 \u0cb5\u0cb0?"
    }
  },
  {
    "path": "blog_exclusive--sericulture-startup-mori-raises--12m-series-a-to-preserve-food-with-silk.html",
    "context": {
      "title": "EXCLUSIVE: Sericulture startup Mori raises $12m Series A to preserve food with silk",
      "first_heading": "EXCLUSIVE: Sericulture startup Mori raises $12m Series A to preserve food with silk"
    }
  },
  {
    "path": "blog_smriti-irani-says-textiles-sector-should-stop-seeking-packages--govt-finances-already-strained---source---business-today.html",
    "context": {
      "title": "Smriti Irani says textiles sector should stop seeking packages, govt finances already strained | Source - Business Today",
      "first_heading": "Smriti Irani says textiles sector should stop seeking packages, govt finances already strained | Source - Business Today"
    }
  },
  {
    "path": "blogs.html",
    "context": {
      "title": "Our Blogs | Silk Association Of India",
      "first_heading": "OUR BLOGS"
    }
  },
  {
    "path": "contact_us.html",
    "context": {
      "title": "Contact Us | Silk Association Of India",
      "first_heading": "CONTACT US"
    }
  },
  {
    "path": "css/451fa095f4501ad908bad77892b9ebc7.css",
    "context": {
      "path": "css/451fa095f4501ad908bad77892b9ebc7.css"
    }
  },
  {
    "path": "css/559e64bf161e61fa0aca6e864c78191d.css",
    "context": {
      "path": "css/559e64bf161e61fa0aca6e864c78191d.css"
    }
  },
  {
    "path": "css/7cd3c01f553780097ebe1c4668033bfe.css",
    "context": {
      "path": "css/7cd3c01f553780097ebe1c4668033bfe.css"
    }
  },
  {
    "path": "css/7e610f95a2d26c26bc901487cdcd9a1c.css",
    "context": {
      "path": "css/7e610f95a2d26c26bc901487cdcd9a1c.css"
    }
  },
  {
    "path": "css/84d4a0216f16f715d9b301db3a8da352.css",
    "context": {
      "path": "css/84d4a0216f16f715d9b301db3a8da352.css"
    }
  },
  {
    "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css",
    "context": {
      "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css"
    }
  },
  {
    "path": "css/c363a15baf9b3719c1570c22b012b369.css",
    "context": {
      "path": "css/c363a15baf9b3719c1570c22b012b369.css"
    }
  },
  {
    "path": "css/d09d646f062b67daeff66ff1410b63fc.css",
    "context": {
      "path": "css/d09d646f062b67daeff66ff1410b63fc.css"
    }
  },
  {
    "path": "css/internal-styles.css",
    "context": {
      "path": "css/internal-styles.css"
    }
  },
  {
    "path": "executive_commitee.html",
    "context": {
      "title": "Executive Committee Member | Silk Association Of India",
      "first_heading": "EXECUTIVE COMMITTEE MEMBERS"
    }
  },
  {
    "path": "gallery.html",
    "context": {
      "title": "Gallery | Silk Association Of India",
      "first_heading": "VIDEOS"
    }
  },
  {
    "path": "genesis.html",
    "context": {
      "title": "Genesis | Silk Association Of India",
      "first_heading": "GENESIS"
    }
  },
  {
    "path": "imgs/026517484daf7868ca18959947d1c839.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/029a73c7400cb9322d119eab8c8195e6.webp",
    "context": {
      "refs": [
        {
          "alt": "AGMofSAI1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/04d084d15b0364e59654b5df59cefccb.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20190618WA0016",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/04fb977966f7b12b3b53091ce72d2bb6.webp",
    "context": {
      "refs": [
        {
          "alt": "deafcdfeebfcdedfbceed",
          "title": ""
        },
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0593f7efabdf163be7a36f0ef3dd62e4.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/077958f5b462d2d0966ebecf37529df7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0ac239c843ed2411bfb9e6b010726798.webp",
    "context": {
      "refs": [
        {
          "alt": "v01I01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0d039547046fd44e2359530e4f01a17f.webp",
    "context": {
      "refs": [
        {
          "alt": "image",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "image",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0ebc2133e84e1b57136656c0de266fef.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImembersvisittoSubbannaGarden",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1549db691bf10ad424f65b7ccb074944.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20200318WA0015",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/16fbdba6ab1c7372f69b327f0c054097.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImemebersdiscussionswithTamilNaduSericulturists",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1c40c00590dc95b98421b11db4f0a906.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1ee08a99585e67a74c6161ec39a09c96.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/20a61f5353d8b18c0349212feee3a281.webp",
    "context": {
      "refs": [
        {
          "alt": "v02I03",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/22218f604456b9deae78a188f91e64ec.webp",
    "context": {
      "refs": [
        {
          "alt": "Covid 19: Crisis in Silk Industry-Role of DOS",
          "title": ""
        },
        {
          "alt": "Covid 19: Crisis in Silk Industry-Role of DOS",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2a61c3774fb641c0693c6c460b70d1da.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20191023WA0028",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2cd2c65ef47baf09f50730815fc03b43.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG4594",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2dd848f0bc346545b40a38c1c80c5b32.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIseminor3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3085686f34c9e863e9e495028e9d8820.webp",
    "context": {
      "refs": [
        {
          "alt": "SeminororganisedbySAIon2382019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3549803b0ebe53e9bcb0d76857dc9a7e.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImembersvisitanddiscussionsatSubbannaGarden",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3a56de57dadad75ba5ca0a6a91a775e0.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIseminor2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3ca2fa3907422c682701e1946e7c1791.gif",
    "context": {
      "refs": [
        {
          "alt": "MrVBalasubramaniyan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/41f31ca1fe073e7e62197bc1d81c6bc5.gif",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/42fefaa6b73c1d91bf3dbaaee4ad8d9b.webp",
    "context": {
      "refs": [
        {
          "alt": "AGMofSAI3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/43bdd92655da31c13d92ebf4d18068a0.webp",
    "context": {
      "refs": [
        {
          "alt": "Appeal to Stakeholders of Sericulture",
          "title": ""
        },
        {
          "alt": "Appeal to Stakeholders of Sericulture",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/47d0710cd3f80a97b5174010e6d2827f.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIseminor1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4803a76d88d020c466a4987207505877.webp",
    "context": {
      "refs": [
        {
          "alt": "image05",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c1c3acd7ec1d13797bedfa261660899.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/513377ddb58d3c4b4b75aa6ff65e6131.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20191212WA0028",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/515e6c918bb0b46ba75c4981ce1bc7ed.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImembersvisittoARMatRamanagara",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/51ad81667060660530a6b149f15dacf7.gif",
    "context": {
      "refs": [
        {
          "alt": "MrRamachandraGowda",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5751e71cba6bac677ef76dd8d4b7daaa.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bb49084105026ce30b4e746f37febca.webp",
    "context": {
      "refs": [
        {
          "alt": "Covid 19 - Impact on Silk Industry | Silk Association of India",
          "title": ""
        },
        {
          "alt": "Covid 19 - Impact on Silk Industry | Silk Association of India",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bca535d8613cbc400db99eacefc805a.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIpressmeet",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5c95a280a0e1bc2c494c5fd494115a0b.webp",
    "context": {
      "refs": [
        {
          "alt": "AGMofSAI4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5d26bc0e2cedff12c81ecda73e4f3cdb.webp",
    "context": {
      "refs": [
        {
          "alt": "v02I04",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/61d71fdec61859f68cf159e68a2981ef.webp",
    "context": {
      "refs": [
        {
          "alt": "MeetingwithDirectorDeptofSericultureTamilNaduon1112019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6284fce8016a81db2ff707f042e05ece.webp",
    "context": {
      "refs": [
        {
          "alt": "image3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6561e72b343f1974af97937b28815e9d.webp",
    "context": {
      "refs": [
        {
          "alt": "AGMofSAI2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/65b0408c2f4166bce54b19723b693d93.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20190618WA0019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6b5097d29cd0d2c140f3efcf242d130f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6b8a7ac02972cd713b04ce966415c7db.webp",
    "context": {
      "refs": [
        {
          "alt": "d594a0e92524469c955ad8fda17ccb7b",
          "title": ""
        },
        {
          "alt": "d594a0e92524469c955ad8fda17ccb7b",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6c7bd7623a710a7d937521c53ce132a7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6e972d3055fd260b3278ff4025f6845c.webp",
    "context": {
      "refs": [
        {
          "alt": "WhatsAppImage20201022at80903PM",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/71f319633c1097a72dd2ce23078f4514.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIMemebersVisittoRamanagaraCocoonMarket",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/722a892af06c73a11a8455ec1869048a.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIseminor4",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/75951de52f54eea9a671924e01bd02ad.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG4614",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/77714d766bc4ffe7ce32acde3f20735f.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImemebersdiscussionwithcocoommarketingofficeratRamanagara",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/778248ca01db681699f0304962a25aac.webp",
    "context": {
      "refs": [
        {
          "alt": "v03I02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/79a5698c2d8dac8e030669f2ea8c52bf.webp",
    "context": {
      "refs": [
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7b00882784f326086745b115235a5770.webp",
    "context": {
      "refs": [
        {
          "alt": "v02I02",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7f410bb810649ce65f398d99c195dc98.webp",
    "context": {
      "refs": [
        {
          "alt": "94c59ffa0afa4bc79ca89d4ca4f57f54",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7fd78b9054f304a422edefa1cd31d07c.webp",
    "context": {
      "refs": [
        {
          "alt": "SeminororganisedbySAIon2382019atKASSIA2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/810cfc207914a15238e023c397abf31a.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20200824WA0013",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/81901a33975123699a50d15c38ab99a1.webp",
    "context": {
      "refs": [
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        },
        {
          "alt": "LogowithMulberyLeaf",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8662450127becb0b89646b2f0070f358.gif",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/89c8f1cb19944b4b24d720307dade5ac.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImembersvisittoSilkwormRearinghouseatTamilNadu",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/89dc83fb64a5e0668fa95c7bfda3d8e9.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImembersvisittofarmarsmulberrygarden",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8affd65f22e3c2179397512833cdbb32.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImemebersvisittoCocoonReelingUnitatTamilNadu",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8cd7856206728e27f9729d7d5a88704a.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20191212WA0029",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/92a7fa7e5893def5d8b7786574b6cad7.webp",
    "context": {
      "refs": [
        {
          "alt": "deafcdfeebfcdedfbceed",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/94d0446811e029af865748f00f10e4e0.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImemebersvisittoHinduprsilktwistingFactory",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/96828cd2046c899f9845d747544eb103.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20190824WA0049",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/96a01e15575a1e0547ef4bb6ccd876a4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a235424a63029569a562e3c63bc9b07d.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20191203WA00071",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a5f977a8f40dcd6b7979994c1bd25210.webp",
    "context": {
      "refs": [
        {
          "alt": "v03I01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8d9c4fe715e6a5cc3e09cf5f460149a.webp",
    "context": {
      "refs": [
        {
          "alt": "Silk Association of India",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/acafa4cd0706fbdf49e4f4871abda95c.webp",
    "context": {
      "refs": [
        {
          "alt": "deafcdfeebfcdedfbceed",
          "title": ""
        },
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/af9e8491773116f1822b375fd6d8f61b.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIMemebersalongwithReelerssubmittedamemorandumtoMinistersMadaswamynottoincludesilkunderGST15122019",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b27107dabaa8f42b1c4f78b46d3cf543.webp",
    "context": {
      "refs": [
        {
          "alt": "AGMofSAI",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b3d67b48233b447207fd06c25d3e7246.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20200605WA0020",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c80b0548dba0036ae490a1c017bf2b2a.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIorganizedfarmersmeetatTamilNadu",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c94a02629071c88637d56681daa244b2.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG4653",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cab93e1288dabb9dcbc0b573d72bc202.gif",
    "context": {
      "refs": [
        {
          "alt": "DrSBDandinPassportphoto",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d02a302ac77c566969a8f5d3e014831d.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20200119WA0007",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d078c6d2ace7a32e508db74f97bf22f3.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20191101WA0092",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d13d0aab723e25a74bde4eb76d5cf787.webp",
    "context": {
      "refs": [
        {
          "alt": "SAImemebersvisitatRamanagara",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d3c095a89525643c7f6aa087e377f33a.webp",
    "context": {
      "refs": [
        {
          "alt": "SAISeminor6",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dcaea401f7542d520402fb50db41efdf.webp",
    "context": {
      "refs": [
        {
          "alt": "v02I01",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/de3f29de4462558e80c18806c7eb2cdf.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20200605WA0018",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dece7527e49cf2e7217974530ba1a35b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e0d002f0e4db6b426a55ae5e9176b819.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e34763980ccafc1701d2c89ef5dbbd1e.webp",
    "context": {
      "refs": [
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e3518f4fe9ab25add741a0a8e72564ae.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG4581",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e5582e0bb90cd8253fd8966848893622.webp",
    "context": {
      "refs": [
        {
          "alt": "Asian Mulberry Fruit Farm and Harvest - Mulberry Juice Processing - Mulberry Cultivation",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e67f20c8b71a4e432423815587e988b0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e82c10a6bce4e11a2a159550b2a08448.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIseminor5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee1f479fab2d8419415de543f993b5a5.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20190824WA0053",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee2b7e33d7d9f5d752636696d5713061.webp",
    "context": {
      "refs": [
        {
          "alt": "Seminororganisedon23122019atKASSIA",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f092cb76b5e7cdd34337ceaf58866756.webp",
    "context": {
      "refs": [
        {
          "alt": "IMG20191102WA0032",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f9e767d0ad8d1ef9266235ff886977a5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fb7984fa296ccc8d3cd207eafb474c89.gif",
    "context": {
      "refs": [
        {
          "alt": "MrCNarayanaswamy",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fce5d3e7223b75604e3ec5d1192687af.gif",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ff66f5a0f97658e496e041beb868b8cb.webp",
    "context": {
      "refs": [
        {
          "alt": "SAIMembersdiscussionswithHindupurFarmers",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "index.html",
    "context": {
      "title": "Home | Silk Association Of India",
      "first_heading": "Silk Association Of India (SAI)"
    }
  },
  {
    "path": "js/03b2eaae6007054a68c38e495f894dba.js",
    "context": {
      "path": "js/03b2eaae6007054a68c38e495f894dba.js"
    }
  },
  {
    "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js",
    "context": {
      "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js"
    }
  },
  {
    "path": "js/0c46896987137b0016246f6bc2243099.js",
    "context": {
      "path": "js/0c46896987137b0016246f6bc2243099.js"
    }
  },
  {
    "path": "js/165d7b0ddfa33362140feea997351b77.js",
    "context": {
      "path": "js/165d7b0ddfa33362140feea997351b77.js"
    }
  },
  {
    "path": "js/16df9ef05001a1741857bf99f5a5738f.js",
    "context": {
      "path": "js/16df9ef05001a1741857bf99f5a5738f.js"
    }
  },
  {
    "path": "js/2a85c11e395a8380b5915443e926b569.js",
    "context": {
      "path": "js/2a85c11e395a8380b5915443e926b569.js"
    }
  },
  {
    "path": "js/34be5330971fdbd18985525bd994b0aa.js",
    "context": {
      "path": "js/34be5330971fdbd18985525bd994b0aa.js"
    }
  },
  {
    "path": "js/35c5f9e096d4da33d2a62031daf14248.js",
    "context": {
      "path": "js/35c5f9e096d4da33d2a62031daf14248.js"
    }
  },
  {
    "path": "js/3d70953a848219e749fedc2cdb906675.js",
    "context": {
      "path": "js/3d70953a848219e749fedc2cdb906675.js"
    }
  },
  {
    "path": "js/3e940a33e44b65c1c0af8bb80a893530.js",
    "context": {
      "path": "js/3e940a33e44b65c1c0af8bb80a893530.js"
    }
  },
  {
    "path": "js/544d012df7acf9c3f0920f67c9e322b9.js",
    "context": {
      "path": "js/544d012df7acf9c3f0920f67c9e322b9.js"
    }
  },
  {
    "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js",
    "context": {
      "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js"
    }
  },
  {
    "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js",
    "context": {
      "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js"
    }
  },
  {
    "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js",
    "context": {
      "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js"
    }
  },
  {
    "path": "js/7260bab328b0ad74815a5efb377bcc67.js",
    "context": {
      "path": "js/7260bab328b0ad74815a5efb377bcc67.js"
    }
  },
  {
    "path": "js/893de96f1b6da546bd7c814964723eca.js",
    "context": {
      "path": "js/893de96f1b6da546bd7c814964723eca.js"
    }
  },
  {
    "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js",
    "context": {
      "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js"
    }
  },
  {
    "path": "js/9455859483e31e4da0e28f10d0742c2a.js",
    "context": {
      "path": "js/9455859483e31e4da0e28f10d0742c2a.js"
    }
  },
  {
    "path": "js/9db10375d298678e53777a2347b87073.js",
    "context": {
      "path": "js/9db10375d298678e53777a2347b87073.js"
    }
  },
  {
    "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js",
    "context": {
      "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js"
    }
  },
  {
    "path": "js/a2261649751fa61b606222c9b2ea3b80.js",
    "context": {
      "path": "js/a2261649751fa61b606222c9b2ea3b80.js"
    }
  },
  {
    "path": "js/b0bade6d42c2702ca85774296cc507c4.js",
    "context": {
      "path": "js/b0bade6d42c2702ca85774296cc507c4.js"
    }
  },
  {
    "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js",
    "context": {
      "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js"
    }
  },
  {
    "path": "js/cecb447a04bbe3e8982190dd6e697120.js",
    "context": {
      "path": "js/cecb447a04bbe3e8982190dd6e697120.js"
    }
  },
  {
    "path": "js/d80b370d82680fc786dcc943a327b9f2.js",
    "context": {
      "path": "js/d80b370d82680fc786dcc943a327b9f2.js"
    }
  },
  {
    "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js",
    "context": {
      "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js"
    }
  },
  {
    "path": "js/eb539083e42509d043ea69d9783854bd.js",
    "context": {
      "path": "js/eb539083e42509d043ea69d9783854bd.js"
    }
  },
  {
    "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js",
    "context": {
      "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js"
    }
  },
  {
    "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js",
    "context": {
      "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js"
    }
  },
  {
    "path": "news_bulletin.html",
    "context": {
      "title": "News Bulletin | Silk Association Of India",
      "first_heading": "NEWS BULLETIN"
    }
  },
  {
    "path": "objectives.html",
    "context": {
      "title": "Objectives | Silk Association Of India",
      "first_heading": "OBJECTIVES"
    }
  },
  {
    "path": "presentation.html",
    "context": {
      "title": "Gallery | Silk Association Of India",
      "first_heading": "PRESENTATIONS"
    }
  },
  {
    "path": "president_desk.html",
    "context": {
      "title": "President Desk | Silk Association Of India",
      "first_heading": "PRESIDENT DESK"
    }
  },
  {
    "path": "product_10thChemistryCBSE.html",
    "context": {
      "title": "10 th Chemistry | CBSE",
      "first_heading": "10 th Chemistry | CBSE"
    }
  },
  {
    "path": "product_PUChemistry.html",
    "context": {
      "title": "PU Chemistry",
      "first_heading": "PU Chemistry"
    }
  },
  {
    "path": "sai_achivement_02.html",
    "context": {
      "title": "SAOI Achievements | Silk Association Of India",
      "first_heading": "ACHIEVEMENTS OF SAI"
    }
  },
  {
    "path": "sai_application_form.html",
    "context": {
      "title": "SAI Membership Application | Silk Association Of India",
      "first_heading": "SILK ASSOCIATION OF INDIAMEMBERSHIP APPLICATION FORM"
    }
  },
  {
    "path": "saoi_volume.html",
    "context": {
      "title": "SAI Newsletter | Silk Association Of India",
      "first_heading": "SILK ASSOCIATION OF INDIA (SAI)NEWSLETTER"
    }
  },
  {
    "path": "workshops_seminars.html",
    "context": {
      "title": "Gallery | Silk Association Of India",
      "first_heading": "WORKSHOP & SEMINARS"
    }
  }
]

Return only a JSON object mapping each path to its new basename (same extension). No other text.