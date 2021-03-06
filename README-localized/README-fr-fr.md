---
page_type: sample
products:
- office-outlook
- office-365
languages:
- csharp
extensions:
  contentType: samples
  createdDate: 6/26/2015 3:03:02 PM
---
# Art Curator pour Windows Phone

Cet exemple indique comment utiliser l’API de messagerie Outlook pour obtenir des messages électroniques et des pièces jointes à partir d’Office 365. Il est conçu pour iOS, [Android](https://github.com/OfficeDev/O365-iOS-ArtCurator), [web (application web Angular)](https://github.com/OfficeDev/O365-Android-ArtCurator) et [Windows Phone](https://github.com/OfficeDev/O365-Angular-ArtCurator). Consultez notre [article sur les moyennes](https://medium.com/office-app-development).

Art Curator propose une nouvelle façon d’afficher votre boîte de réception. Imaginez que vous êtes propriétaire d’une entreprise qui vend des tee-shirts artistiques. En tant que propriétaire de l’entreprise, vous recevez de nombreux messages électroniques de la part d’artistes comportant des conceptions qu’ils tentent de vous vendre. Au lieu d’utiliser Outlook et d’ouvrir chaque message individuellement, de télécharger l’image jointe, puis de l’ouvrir pour l’afficher, vous pouvez utiliser Art Curator pour avoir un premier aperçu des pièces jointes de votre boîte de réception (limité aux fichiers .jpg et .png) afin de sélectionner et choisir les conceptions qui vous plaisent de façon plus efficace.

[![Capture d’écran Art Curator\](./README Assets/AC\_WinPhone.png)](https://youtu.be/4LOvkweDfhY "Cliquez pour voir l’exemple en action.")

Cet exemple illustre les opérations suivantes de l’**API de courrier Outlook** :
* [Obtenir des dossiers](https://msdn.microsoft.com/office/office365/APi/mail-rest-operations#GetFolders)
* [Obtenir des messages](https://msdn.microsoft.com/office/office365/APi/mail-rest-operations#Getmessages) (notamment le filtrage et l’utilisation de la fonction select)
* [Obtenir des pièces jointes](https://msdn.microsoft.com/office/office365/APi/mail-rest-operations#GetAttachments)
* [les messages de mise à jour](https://msdn.microsoft.com/office/office365/APi/mail-rest-operations#Updatemessages)
* [Créer et envoyer des messages](https://msdn.microsoft.com/office/office365/APi/mail-rest-operations#Sendmessages) (avec et sans pièce jointe) 

<a name="prerequisites"></a>
## Conditions préalables

Cet exemple nécessite les éléments suivants :  

  - Windows 8.1
  - Visual Studio 2013 avec la mise à jour 3
  - [Outils des API Office 365 version 1.4.50428.2](http://aka.ms/k0534n)
  - Un [site du développeur Office 365](http://aka.ms/ro9c62)
  - Un [compte développeur d’applications Windows](https://appdev.microsoft.com/StorePortals/en-us/Account/signup/start)

### Configurer l’exemple

Procédez comme suit pour configurer l’exemple.

   1. Ouvrez le fichier **O365-Windows-Phone-Art-Curator.sln** à l’aide de Visual Studio 2013.
   2. Générez la solution. La fonctionnalité de restauration du package NuGet chargera les assemblys répertoriés dans le fichier packages.config.
   3. Inscrivez et configurez l’application pour utiliser les services Office 365 (détaillés ci-dessous).

### Inscrire l’application pour utiliser les API Office 365

Vous pouvez effectuer cette action via Office 365 API Tools pour Visual Studio (qui automatise le processus d’inscription). Veillez à télécharger et à installer les outils d’API Office 365 à partir de la galerie Visual Studio.

**Remarque** : Si vous détectez des erreurs lors de l’installation des packages (par exemple, *Impossible de trouver « Microsoft.IdentityModel.Clients.ActiveDirectory »*), vérifiez que le chemin d’accès local où vous avez placé la solution n’est pas trop long/profond. Pour résoudre ce problème, il vous suffit de déplacer la solution dans un dossier plus près du répertoire racine de votre lecteur.

   1. Dans la fenêtre Explorateur de solutions, choisissez le projet **O365-Windows-Phone-Art-Curator** -> Ajouter -> Service connecté.
   2. Une boîte de dialogue Gestionnaire de services s’affiche. Choisissez Office 365 et inscrivez votre application.
   3. Dans la boîte de dialogue de connexion, saisissez le nom d’utilisateur et le mot de passe pour votre client Office 365. Nous vous recommandons d’utiliser votre site de développeur Office 365. Ce nom d’utilisateur suit souvent le modèle {nom\_utilisateur}@{client}.onmicrosoft.com. Si vous ne disposez pas d’un site de développeur, vous pouvez obtenir un site de développeur gratuit dans le cadre de vos avantages MSDN ou souscrire une version d’évaluation gratuite. N’oubliez pas que l’utilisateur doit être un administrateur client, mais que pour les clients créés dans le cadre d’un site de développeur Office 365, cela peut déjà être le cas. En outre, les comptes de développeur sont généralement limités à une connexion.
   4. Une fois que vous êtes connecté, vous verrez la liste de tous les services. Initialement, aucune autorisation n’est sélectionnée, car l’application n’est pas encore inscrite pour utiliser les services. 
   5. Pour vous inscrire aux services utilisés dans cet exemple, choisissez les autorisations suivantes :  
      * (Messagerie) : *Envoyer un courrier électronique en tant qu’utilisateur*
      * (Messagerie) : *Lire et écrire un courrier électronique d’utilisateur*
   6. Cliquez sur OK dans la boîte de dialogue Gestionnaire de services.

<a name="build"></a>
## Exécuter l’application

Une fois que vous avez chargé la solution dans Visual Studio, appuyez sur F5 pour la générer et la déployer.

<a name="understand"></a>
## Comprendre le code
   
### Limites

Les fonctionnalités suivantes ne sont pas incluses dans la version actuelle.

* Prise en charge de formats de fichiers autres que .png et .jpg
* Gestion d’un courrier électronique unique avec plusieurs pièces jointes
* Pagination (réception de plus de 50 courriers électroniques)
* Gestion de l’unicité des noms de dossiers
* Dossier de soumission devant être un dossier de niveau supérieur  

<a name="questions-and-comments"></a>
## Questions et commentaires

- Si vous rencontrez des difficultés pour exécuter cet exemple, [consignez un problème](https://github.com/OfficeDev/O365-WinPhone-ArtCurator/issues).
- Pour des questions générales relatives aux API Office 365, publiez sur [Stack Overflow](http://stackoverflow.com/). Posez vos questions avec les balises \[office365].
  
<a name="additional-resources"></a>
## Ressources supplémentaires

* [Présentation de la plateforme des API Office 365](http://msdn.microsoft.com/office/office365/howto/platform-development-overview)
* [Centre des développeurs Office](http://dev.office.com/)
* [Art Curator pour iOS](https://github.com/OfficeDev/O365-iOS-ArtCurator)
* [Art Curator pour Android](https://github.com/OfficeDev/O365-Android-ArtCurator)
* [Art Curator pour le web](https://github.com/OfficeDev/O365-Angular-ArtCurator)

## Copyright

Copyright (c) Microsoft. Tous droits réservés.
 


Ce projet a adopté le [code de conduite Open Source de Microsoft](https://opensource.microsoft.com/codeofconduct/). Pour en savoir plus, reportez-vous à la [FAQ relative au code de conduite](https://opensource.microsoft.com/codeofconduct/faq/) ou contactez [opencode@microsoft.com](mailto:opencode@microsoft.com) pour toute question ou tout commentaire.
