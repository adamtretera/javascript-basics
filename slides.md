---
theme: geist
highlighter: shiki
---

# Javascript základy
Vše potřebné pro vyvoj appky React ⚛️

---

# První script

- [ ] 🛠 Pro první testovaní budeme používat [Stackblitz](https://stackblitz.com/)
- [ ] Pokud nemáte **GitHub** založte si ho pod školním mailem 
- [ ] Dále budeme pracovat s IDE **WebStorm** (popř. VS code)
- [ ] [Jet brains licence](https://education.github.com/)
---
# Proč je JS fajn?

-   😎 Jeden z nejvíce používaných a chtěných 


Read more about [Slidev](https://sli.dev)

---

# Navigation

Hover over the bottom-left corner of your screen to see the control panel.

### Keyboard Shortcuts

| shortcut                                             | purpose                     |
| ---------------------------------------------------- | --------------------------- |
| <KBD>space</KBD> / <KBD>tab</KBD> / <KBD>right</KBD> | next animation or slide     |
| <KBD>left</KBD>                                      | previous animation or slide |
| <KBD>up</KBD>                                        | previous slide              |
| <KBD>down</KBD>                                      | next slide                  |

---

# Code

Use `code` snippets and get automatic highlighting!

```ts
// type
interface User {
    id: number;
    firstName: string;
    lastName: string;
    role: string;
}

// function
function updateUser(id: number, update: Partial<User>) {
    const user = getUser(id);
    const newUser = { ...user, ...update };
    saveUser(id, newUser);
}
```

---

# Theme Components

## Button

<Button>Button</Button>

## Keyboard Input

<KBD command shift>P</KBD>

## Note

<Note>Note</Note>

---

# Learn More

[Documentation](https://sli.dev) / [GitHub Repository](https://github.com/slidevjs/slidev)