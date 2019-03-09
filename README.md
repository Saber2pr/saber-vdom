# saber-vdom

> saber-vdom

```bash
# from npm
npm install saber-vdom

# from github
git clone https://github.com/Saber2pr/saber-vdom.git
```

```ts
const Content = (content: string, uuid: string): Element<'p'> => ({
  uuid: uuid,
  type: 'p',
  props: {
    innerHTML: content
  }
})

const Button = (
  name: string,
  uuid: string,
  onclick: () => any
): Element<'button'> => ({
  type: 'button',
  uuid: uuid,
  props: {
    innerHTML: name,
    onclick
  }
})

const Line = (...children: Element<any>[]): Element<'div'> => ({
  type: 'div',
  uuid: 'xaadada',
  children
})

const Tab = (select: 'first' | 'second'): Element<'div'> => ({
  type: 'div',
  uuid: '004',
  children: [
    Line(
      Button('first', '0xxx0xx1', () => update('first')),
      Button('second', '0xxx0xxeqeq1', () => update('second'))
    ),
    Line(
      select === 'first'
        ? Content('1. this is first.', 'abcdef')
        : Content('2. this is second.', 'abcdef')
    )
  ]
})

const update = (select: 'first' | 'second') =>
  render(Tab(select), document.getElementById('root'))
update('first')
```

---

## start

```bash
npm install
```

```bash
npm start

npm run dev

```

> Author: saber2pr

---

## develope and test

> you should write ts in /src

> you should make test in /src/test

> export your core in /src/index.ts!
