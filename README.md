{
    "name": "Zaluea",
    "description": "Zaluea is made for bypassing web restrictions.",
    "repository": "https://github.com/TheIcy/Zaluea",
    "logo": "https://github.com/TheIcy/Zaluea/blob/main/Site/images/logo.png?raw=true",
    "keywords": ["zaluea", "games", "Ultraviolet"]
}
(async() => {
    await import('./index.mjs');
  })();
  import Server from 'bare-server-node';
import http from 'http';
import nodeStatic from 'node-static';


const bare =  new Server('/bare/', '');
const serve = new nodeStatic.Server('Site/');
const server = http.createServer();

server.on('request', (request, response) => {
    if (bare.route_request(request, response)) return true;
    serve.serve(request, response);
});

server.on('upgrade', (req, socket, head) => {
	if(bare.route_upgrade(req, socket, head))return;
	socket.end();
});

server.listen(process.env.PORT || 8080);
{
  "name": "Zaluea-Proxy",
  "lockfileVersion": 2,
  "requires": true,
  "packages": {
    "": {
      "dependencies": {
        "bare-server-node": "github:tomphttp/bare-server-node",
        "node-static": "^0.7.11"
      }
    },
    "node_modules/bare-server-node": {
      "version": "0.0.1",
      "resolved": "git+ssh://git@github.com/tomphttp/bare-server-node.git#ebf421fd2a350c076e5aeea1fc8814da4f458853",
      "license": "GPL-3.0",
      "dependencies": {
        "commander": "^9.0.0",
        "fetch-headers": "^3.0.1"
      }
    },
    "node_modules/colors": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/colors/-/colors-1.4.0.tgz",
      "integrity": "sha512-a+UqTh4kgZg/SlGvfbzDHpgRu7AAQOmmqRHJnxhRZICKFUT91brVhNNt58CMWU9PsBbv3PDCZUHbVxuDiH2mtA==",
      "engines": {
        "node": ">=0.1.90"
      }
    },
    "node_modules/commander": {
      "version": "9.1.0",
      "resolved": "https://registry.npmjs.org/commander/-/commander-9.1.0.tgz",
      "integrity": "sha512-i0/MaqBtdbnJ4XQs4Pmyb+oFQl+q0lsAmokVUH92SlSw4fkeAcG3bVon+Qt7hmtF+u3Het6o4VgrcY3qAoEB6w==",
      "engines": {
        "node": "^12.20.0 || >=14"
      }
    },
    "node_modules/fetch-headers": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/fetch-headers/-/fetch-headers-3.0.1.tgz",
      "integrity": "sha512-Kq+NyED/wLgT29St7aW47gAWg8EmmE5QmhwQ5RmPRULYLqpglA7Kc/ZnbqXu2vhH6mw1koikew2g94WiHLPmpA==",
      "funding": [
        {
          "type": "github",
          "url": "https://github.com/sponsors/jimmywarting"
        },
        {
          "type": "github",
          "url": "https://paypal.me/jimmywarting"
        }
      ],
      "engines": {
        "node": ">=12.20"
      }
    },
    "node_modules/mime": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/mime/-/mime-1.6.0.tgz",
      "integrity": "sha512-x0Vn8spI+wuJ1O6S7gnbaQg8Pxh4NNHb7KSINmEWKiPE4RKOplvijn+NkmYmmRgP68mc70j2EbeTFRsrswaQeg==",
      "bin": {
        "mime": "cli.js"
      },
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/minimist": {
      "version": "0.0.10",
      "resolved": "https://registry.npmjs.org/minimist/-/minimist-0.0.10.tgz",
      "integrity": "sha1-3j+YVD2/lggr5IrRoMfNqDYwHc8="
    },
    "node_modules/node-static": {
      "version": "0.7.11",
      "resolved": "https://registry.npmjs.org/node-static/-/node-static-0.7.11.tgz",
      "integrity": "sha512-zfWC/gICcqb74D9ndyvxZWaI1jzcoHmf4UTHWQchBNuNMxdBLJMDiUgZ1tjGLEIe/BMhj2DxKD8HOuc2062pDQ==",
      "dependencies": {
        "colors": ">=0.6.0",
        "mime": "^1.2.9",
        "optimist": ">=0.3.4"
      },
      "bin": {
        "static": "bin/cli.js"
      },
      "engines": {
        "node": ">= 0.4.1"
      }
    },
    "node_modules/optimist": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/optimist/-/optimist-0.6.1.tgz",
      "integrity": "sha1-2j6nRob6IaGaERwybpDrFaAZZoY=",
      "dependencies": {
        "minimist": "~0.0.1",
        "wordwrap": "~0.0.2"
      }
    },
    "node_modules/wordwrap": {
      "version": "0.0.3",
      "resolved": "https://registry.npmjs.org/wordwrap/-/wordwrap-0.0.3.tgz",
      "integrity": "sha1-o9XabNXAvAAI03I0u68b7WMFkQc=",
      "engines": {
        "node": ">=0.4.0"
      }
    }
  },
  "dependencies": {
    "bare-server-node": {
      "version": "git+ssh://git@github.com/tomphttp/bare-server-node.git#ebf421fd2a350c076e5aeea1fc8814da4f458853",
      "from": "bare-server-node@github:tomphttp/bare-server-node",
      "requires": {
        "commander": "^9.0.0",
        "fetch-headers": "^3.0.1"
      }
    },
    "colors": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/colors/-/colors-1.4.0.tgz",
      "integrity": "sha512-a+UqTh4kgZg/SlGvfbzDHpgRu7AAQOmmqRHJnxhRZICKFUT91brVhNNt58CMWU9PsBbv3PDCZUHbVxuDiH2mtA=="
    },
    "commander": {
      "version": "9.1.0",
      "resolved": "https://registry.npmjs.org/commander/-/commander-9.1.0.tgz",
      "integrity": "sha512-i0/MaqBtdbnJ4XQs4Pmyb+oFQl+q0lsAmokVUH92SlSw4fkeAcG3bVon+Qt7hmtF+u3Het6o4VgrcY3qAoEB6w=="
    },
    "fetch-headers": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/fetch-headers/-/fetch-headers-3.0.1.tgz",
      "integrity": "sha512-Kq+NyED/wLgT29St7aW47gAWg8EmmE5QmhwQ5RmPRULYLqpglA7Kc/ZnbqXu2vhH6mw1koikew2g94WiHLPmpA=="
    },
    "mime": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/mime/-/mime-1.6.0.tgz",
      "integrity": "sha512-x0Vn8spI+wuJ1O6S7gnbaQg8Pxh4NNHb7KSINmEWKiPE4RKOplvijn+NkmYmmRgP68mc70j2EbeTFRsrswaQeg=="
    },
    "minimist": {
      "version": "0.0.10",
      "resolved": "https://registry.npmjs.org/minimist/-/minimist-0.0.10.tgz",
      "integrity": "sha1-3j+YVD2/lggr5IrRoMfNqDYwHc8="
    },
    "node-static": {
      "version": "0.7.11",
      "resolved": "https://registry.npmjs.org/node-static/-/node-static-0.7.11.tgz",
      "integrity": "sha512-zfWC/gICcqb74D9ndyvxZWaI1jzcoHmf4UTHWQchBNuNMxdBLJMDiUgZ1tjGLEIe/BMhj2DxKD8HOuc2062pDQ==",
      "requires": {
        "colors": ">=0.6.0",
        "mime": "^1.2.9",
        "optimist": ">=0.3.4"
      }
    },
    "optimist": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/optimist/-/optimist-0.6.1.tgz",
      "integrity": "sha1-2j6nRob6IaGaERwybpDrFaAZZoY=",
      "requires": {
        "minimist": "~0.0.1",
        "wordwrap": "~0.0.2"
      }
    },
    "wordwrap": {
      "version": "0.0.3",
      "resolved": "https://registry.npmjs.org/wordwrap/-/wordwrap-0.0.3.tgz",
      "integrity": "sha1-o9XabNXAvAAI03I0u68b7WMFkQc="
    }
  }
}
{
  "dependencies": {
    "bare-server-node": "github:tomphttp/bare-server-node",
    "node-static": "^0.7.11"
  }
}
