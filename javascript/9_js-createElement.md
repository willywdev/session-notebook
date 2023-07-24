# JavaScript createElement

`createElement` erstellt ein HTML Element in JavaScript. Dies kann beispielsweise bei dynamischen Postings automatisiert werden.

```javascript
document.createElement("li");
```

Durch den obigen Code wird das Element nur erstellt, es wird noch nicht platziert oder angezeigt. Es ist unsichtbar.

Mit `.append()` kann das erstellte Element einem anderen Element (dem Eltern-Element) hinzugefügt werden. Das Element wird dabei als letztes Element in der Hierarchie hinzugefügt.

```javascript
list.append(listItem);
```

Es gibt auch `.innerHTML`, jedoch wird es aus Sicherheitsgründen nicht empfohlen, da es Angriffe ermöglichen kann.
