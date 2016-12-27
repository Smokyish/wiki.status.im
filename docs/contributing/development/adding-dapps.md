# Adding DApps

During the Alpha we are accepting example DApps as default contacts, to add your DApp to Status, you need to ensure it works on testnet (Ropsten) and submit a single commit pull request to [status-react](http://github.com/status-im/status-react) with the following:

- Place a nice 85x85px icon of your DApp to `images/contacts` directory. The file should be named the same as your DApp, for example `my-dapp.png`.

- Add information about this icon to `src/status_im/resources.cljs`, for example:
```
(def contacts
  {:auction-house (js/require "./images/contacts/auction-house.png")
   :my-dapp (js/require "./images/contacts/my-dapp.png")})
```

- Add your DApp to the list of existing DApps (`resources/default_contacts.json`):

```
[
    ...,

    {"id": "my-dapp",
     "name": "My DApp",
     "photo-path": "contacts://my-dapp",
     "dapp?": true,
     "dapp-url": "http://link-to-your-dapp.com"}
]
```

- Submit PR