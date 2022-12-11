# Lern-Bericht
## von Joel Fritschi

### Einleitung

Encryption ist ein Verfahren, das dazu verwendet wird, Informationen so zu verschlüsseln, dass sie nur von autorisierten Personen gelesen werden können. Es wird seit Jahrhunderten verwendet, um die Kommunikation zwischen Personen oder Gruppen zu schützen und die Vertraulichkeit von Informationen zu gewährleisten. In der heutigen digitalen Welt spielt Encryption eine wichtige Rolle bei der Sicherung von Daten, die über das Internet gesendet werden, und beim Schutz von Computer- und Netzwerksystemen vor unbefugtem Zugriff. In diesem Lernbericht werden wir uns damit befassen, wie Encryption funktioniert und warum sie so wichtig ist.

### Was habe ich gelernt?

Passwörter sollten gehasht werden, um sie vor unbefugtem Zugriff zu schützen.

### Beschreibung

✍️ Verwenden Sie drei verschiedene Medien, um zu zeigen, was Sie gelernt haben. Zum Beispiel:

Wenn Passwörter im Klartext gespeichert werden, können sie von jedem, der Zugriff auf die Datenbank hat, gelesen werden. Wenn sie jedoch gehasht werden, werden sie in eine verschlüsselte Form umgewandelt, die nur durch die Anwendung eines bestimmten Algorithmus wieder in lesbare Form gebracht werden kann. Dies bedeutet, dass selbst wenn jemand Zugriff auf die gehashten Passwörter hat, er sie nicht lesen kann, ohne den Algorithmus zu kennen. Gehashte Passwörter sind daher sicherer als Passwörter im Klartext und sollten immer verwendet werden, wenn Passwörter gespeichert werden.

```java
import java.security.MessageDigest;

public class PasswordHasher {
  public static void main(String[] args) {
    String password = "mypassword";

    // Verwenden des SHA-256-Algorithmus, um das Passwort zu hashen
    MessageDigest digest = MessageDigest.getInstance("SHA-256");
    byte[] hash = digest.digest(password.getBytes(StandardCharsets.UTF_8));

    // Konvertiert das Hash in einen lesbaren Hexadezimalwert
    String hexHash = bytesToHex(hash);
    System.out.println("Gehashtes Passwort: " + hexHash);
  }

  private static String bytesToHex(byte[] hash) {
    StringBuilder hexString = new StringBuilder();
    for (byte b : hash) {
      String hex = Integer.toHexString(0xff & b);
      if (hex.length() == 1) {
        hexString.append('0');
      }
      hexString.append(hex);
    }
    return hexString.toString();
  }
}
```
* Ein deutliches, aussagekräftiges Bild oder eine kommentierte Bildschirm-Aufnahme
* Ein gut dokumentierter Code-Fetzen
* Ein Link zu einem *selbst aufgenommenen* youtube-Video oder `.gif`.

### Verifikation

✍️ Erklären Sie kurz und bündig, inwiefern die von Ihnen verwendeten Medien zeigen, was Sie gelernt haben.

# Reflektion zum Arbeitsprozess

👍 Überlegen Sie sich jeweils etwas, was gut an Ihrer Arbeit lief; 

👎 und etwas, was nicht gut lief.

**VBV**: ✍️ Formulieren Sie davon ausgehend einen *handelbaren* Verbesserungsvorschlag.
