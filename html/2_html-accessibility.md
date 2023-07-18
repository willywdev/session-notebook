# Accessibility

Accessibility (Barrierefreiheit) ist wichtig, da viele Menschen Behinderungen haben oder besondere Anforderungen beim Zugriff auf Webseiten haben. Barrierefreie Gestaltung ermöglicht es allen Nutzern, die Seite effektiv zu nutzen, einschließlich solcher, die Screenreader verwenden, die Schriftgröße anpassen müssen oder die Seite nur mit einer Hand bedienen können.

Arten von Barrieren:

- Permanent: Behinderungen oder Einschränkungen, die dauerhaft bestehen.
- Temporary: Vorübergehende Einschränkungen, z.B. eine verletzte Hand.
- Situational: Situationsspezifische Einschränkungen, z.B. ein lauter Ort, an dem Audioinhalte nicht gut gehört werden können.

Accessibility ToDo's:

1. Semantisches HTML nutzen: Verwende sinnvolle HTML-Tags, um die Struktur der Seite klarer zu machen und Screenreadern zu helfen, die Seite besser zu interpretieren.

2. Bilder Alt-Text nutzen: Verwende den `alt`-Attribut bei Bildern, um eine Beschreibung des Bildinhalts bereitzustellen. Halte den Alt-Text möglichst kurz, da er komplett vorgelesen wird. Für nicht relevante Bilder kann das `alt`-Attribut auch weggelassen werden.

3. SVGs accessible machen: SVGs haben kein `alt`-Attribut. Man kann `aria-label` verwenden, um HTML-Elementen, die nicht accessible sind (z.B. wenn sie kein `alt`-Attribut haben), eine Beschreibung zu geben. Zum Beispiel: `<a href="#" aria-label="Go to profile page">`.

4. `screenreader only`: Man kann bestimmte Elemente so gestalten, dass sie nur für den Screenreader sichtbar sind und für normale Benutzer nicht angezeigt werden.

Die Beachtung von Accessibility-Prinzipien ist wichtig, um sicherzustellen, dass die Webseite für alle Nutzer zugänglich und benutzbar ist.
