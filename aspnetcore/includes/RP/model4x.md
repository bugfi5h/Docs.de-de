<a name="scaffold"></a>
### <a name="scaffold-the-movie-model"></a>Erstellen des Filmmodells

* Öffnen Sie ein Befehlsfenster im Projektverzeichnis (das Verzeichnis mit den Dateien *Program.cs*, *Startup.cs*, und *CSPROJ*).
* Führen Sie den folgenden Befehl aus:

  ```console
  dotnet aspnet-codegenerator razorpage -m Movie -dc MovieContext -udl -outDir Pages/Movies --referenceScriptLibraries
  ```
  
Wenn Sie eine Fehlermeldung erhalten, müssen Sie Folgendes tun:
  ```
No executable found matching command "dotnet-aspnet-codegenerator"
  ```

Öffnen Sie ein Befehlsfenster im Projektverzeichnis (das Verzeichnis mit den Dateien *Program.cs*, *Startup.cs*, und *CSPROJ*).