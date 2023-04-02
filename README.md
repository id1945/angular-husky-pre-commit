# Clean code - Husky and Git Hooks in Angular application

https://githooks.com
https://typicode.github.io/husky

>Assume that we are missing the sign semicolon
[![Precommit validations using husky and lint-staged](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-1.png)](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-1.png)
>git add .
>git commit -m "test"
[![Precommit validations using husky and lint-staged](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-2.png)](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-2.png)
>fixed
[![Precommit validations using husky and lint-staged](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-3.png)](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-3.png)
>git push origin master
[![Precommit validations using husky and lint-staged](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-4.png)](https://raw.githubusercontent.com/id1945/angular-precommit/master/clean-code-4.png)

# Install husky

### install
```
npm i husky -D
```

### enable git hook
```
npx husky install
```

### add script into package.json
```
npm pkg set scripts.prepare="husky install"
```


### modify pre-commit
```
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

npx lint-staged --no-stash -q -d
```


# Install tslint lint-staged codelyzer

### install
```
npm i tslint lint-staged codelyzer -D
```

### modify package.json
```javascript
"lint-staged": {
    "*.ts": "tslint -p ./tsconfig.json"
}
```

### add tslint.json
```json
{
    "extends": "tslint:recommended",
    "rulesDirectory": [
      "codelyzer"
    ],
    "rules": {
      "align": {
        "options": [
          "parameters",
          "statements"
        ]
      },
      "array-type": false,
      "arrow-return-shorthand": true,
      "curly": true,
      "deprecation": {
        "severity": "warning"
      },
      "eofline": true,
      "import-blacklist": [
        true,
        "rxjs/Rx"
      ],
      "import-spacing": true,
      "indent": {
        "options": [
          "spaces"
        ]
      },
      "max-classes-per-file": false,
      "max-line-length": [
        true,
        140
      ],
      "member-ordering": [
        true,
        {
          "order": [
            "static-field",
            "instance-field",
            "static-method",
            "instance-method"
          ]
        }
      ],
      "no-console": [
        true,
        "debug",
        "info",
        "time",
        "timeEnd",
        "trace"
      ],
      "no-empty": false,
      "no-inferrable-types": [
        true,
        "ignore-params"
      ],
      "no-non-null-assertion": true,
      "no-redundant-jsdoc": true,
      "no-switch-case-fall-through": true,
      "no-var-requires": false,
      "object-literal-key-quotes": [
        true,
        "as-needed"
      ],
      "quotemark": [
        true,
        "single"
      ],
      "semicolon": {
        "options": [
          "always"
        ]
      },
      "space-before-function-paren": {
        "options": {
          "anonymous": "never",
          "asyncArrow": "always",
          "constructor": "never",
          "method": "never",
          "named": "never"
        }
      },
      "typedef": [
        true,
        "call-signature"
      ],
      "typedef-whitespace": {
        "options": [
          {
            "call-signature": "nospace",
            "index-signature": "nospace",
            "parameter": "nospace",
            "property-declaration": "nospace",
            "variable-declaration": "nospace"
          },
          {
            "call-signature": "onespace",
            "index-signature": "onespace",
            "parameter": "onespace",
            "property-declaration": "onespace",
            "variable-declaration": "onespace"
          }
        ]
      },
      "variable-name": {
        "options": [
          "ban-keywords",
          "check-format",
          "allow-pascal-case"
        ]
      },
      "whitespace": {
        "options": [
          "check-branch",
          "check-decl",
          "check-operator",
          "check-separator",
          "check-type",
          "check-typecast"
        ]
      },
      "component-class-suffix": true,
      "contextual-lifecycle": true,
      "directive-class-suffix": true,
      "no-conflicting-lifecycle": true,
      "no-host-metadata-property": true,
      "no-input-rename": true,
      "no-inputs-metadata-property": true,
      "no-output-native": true,
      "no-output-on-prefix": true,
      "no-output-rename": true,
      "no-outputs-metadata-property": true,
      "template-banana-in-box": true,
      "template-no-negated-async": true,
      "use-lifecycle-interface": true,
      "use-pipe-transform-interface": true,
      "directive-selector": [
        true,
        "attribute",
        "app",
        "camelCase"
      ],
      "component-selector": [
        true,
        "element",
        "app",
        "kebab-case"
      ]
    }
}
```

[![Precommit validations using husky and lint-staged](https://img.youtube.com/vi/yvZEAhwWVKU/maxresdefault.jpg)](http://www.youtube.com/watch?v=yvZEAhwWVKU)
