# CSS Responsive

Responsive Design bezieht sich darauf, wie eine Website auf verschiedenen Geräten und Bildschirmgrößen gut angezeigt wird. Ziel ist es, dass die Website auf Mobilgeräten, Tablets und Desktops gut lesbar und bedienbar ist, ohne dass der Benutzer ständig hin- und herzoomen oder scrollen muss.

## Responsive CSS Units

Statt statischer Pixel sollte man relative Einheiten verwenden, um das Design flexibler und anpassungsfähiger zu machen. Einige wichtige relative Einheiten sind:

- `vw` (Viewport Width): entspricht einem Prozent der Viewport-Breite.
- `vh` (Viewport Height): entspricht einem Prozent der Viewport-Höhe.
- `em` (Relative to Parent Element): entspricht der Schriftgröße des Elternelements.
- `rem` (Relative to Root Element): entspricht der Schriftgröße des Root-Elements (html-Element).
- `%` (Percentage): entspricht einem Prozent der Größe des Elternelements.

Es ist ratsam, relative Einheiten für Abmessungen wie Breite, Höhe und Margins/Paddings zu verwenden, da sie sich besser an verschiedene Bildschirmgrößen anpassen können.

## Media Queries

Media Queries sind Bedingungen, die basierend auf bestimmten Viewport- oder Geräteparametern (z. B. Bildschirmbreite) bestimmte CSS-Regeln aktivieren oder deaktivieren. Mit Media Queries kann man das Layout und Styling einer Website an verschiedene Bildschirmgrößen und Geräte anpassen.

Beispiel:

```css
@media (min-width: 768px) {
  /* Hier kommen die CSS-Regeln für größere Bildschirme */
}
```

Mit den Media Queries kann man sogenannte "Breakpoints" definieren, bei denen das Design der Website für bestimmte Bildschirmgrößen angepasst wird. Es ist üblich, mit kleineren Breakpoints zu beginnen und sich dann zu größeren zu bewegen, um ein mobiles-first-Design zu implementieren. Mobile-first bedeutet, dass das grundlegende Design und Layout für mobile Geräte entwickelt werden und dann für größere Geräte angepasst wird.

Zusätzlich können Media Queries auch weitere Parameter wie `prefers-color-scheme` verwenden, um das Farbschema der Website an die Vorlieben des Benutzers anzupassen, z. B. für den Dark Mode.

Insgesamt ermöglichen responsive CSS Units und Media Queries eine bessere Anpassung und Darstellung einer Website auf verschiedenen Geräten und sorgen für eine bessere Benutzererfahrung.
