# Lern-Bericht Encyption
## von Joel Fritschi

### Einleitung

Encryption ist ein Verfahren, das dazu verwendet wird, Informationen so zu verschlüsseln, dass sie nur von autorisierten Personen gelesen werden können. Es wird seit Jahrhunderten verwendet, um die Kommunikation zwischen Personen oder Gruppen zu schützen und die Vertraulichkeit von Informationen zu gewährleisten. In der heutigen digitalen Welt spielt Encryption eine wichtige Rolle bei der Sicherung von Daten, die über das Internet gesendet werden, und beim Schutz von Computer- und Netzwerksystemen vor unbefugtem Zugriff. In diesem Lernbericht werden wir uns damit befassen, wie Encryption funktioniert und warum sie so wichtig ist.

### Was habe ich gelernt?

Passwörter sollten gehasht werden, um sie vor unbefugtem Zugriff zu schützen.

### Beschreibung

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
### Verifikation

Im beschreibenden Text zeige ich auf, dass ich das Thema verstanden habe und im Code Beispiel zeige ich auf wie es umgesetzt werden könnte.

# Reflektion zum Arbeitsprozess

👍 Ich verstand schnell was die verschiedenen Gefahren bedeuten und wie diese Ausgenützt werden können. Also konnte ich mir schnell ein Bild davon machen wie die Probleme angegangen werden könnten.

👎 Leider habe ich oft die Zeit etwas falsch eingeschätzt. Dadurch kam ich oft in Verzug mit Aufträgen, da ich mir viel Zeit für einen Auftrag nahm und dann für den nächsten zu wenig Zeit hatte.
In Zukunft würde ich mir zuerst alle Aufträge anschauen die wir erledigen müssen und dann selber abschätzen wie viel Zeit ich pro Auftrag haben darf, sodass die anderen Aufträge nicht vernachlässigt werden.
