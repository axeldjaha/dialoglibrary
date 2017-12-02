# Avant propos
Les Classes et interfaces de toute librairie 'axeldjaha' commencent toujours par AD (Axel Djaha).
# Description
Librairie pour interagir avec l'utilisateur dans une boîte de dialogue.
# Gradle
compile 'axeldjaha.library:dialog:1.2'
# Concept
![alt text](https://github.com/axeldjaha/dialoglibrary/blob/master/concepte.png?raw=true)
# Exemple 1
![alt text](https://github.com/axeldjaha/dialoglibrary/blob/master/Exemple%201.png?raw=true)

        /**
         * On crée la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit et on personnalise les éléments qu'on veut afficher
         * on définit éventuellement un écouteur d'évènement pour les différents boutons du footer
         * et on affiche la boîte de dialogue ainsi créée.
         */
        ADDialog.newInstance(getSupportFragmentManager())
                .setHeaderText("Position")
                .setHeaderIcon(getResources().getDrawable(R.drawable.position))
                .setHeaderTextColor(getResources().getColor(R.color.blanc))
                .setHeaderBackgroundColor(getResources().getColor(R.color.bleu))
                .setBodyText("Activer la localisation ?")
                .setPositiveButtonText("Oui")
                .setNegativeButtonText("Non")
                .setNeutralButtonText("Plus tard")
                .setFooterTextColor(getResources().getColor(R.color.bleu))
                .setFooterBackgroundColor(getResources().getColor(R.color.gray_light))
                .setListener(new ADDialogListener() {
                    @Override
                    public void onADPositiveButtonClick(String action) {
                        //bouton positif cliqué, faire qqch ici
                    }

                    @Override
                    public void onADNegativeButtonClick(String action) {
                        //bouton négatif cliqué, faire qqch ici
                    }

                    @Override
                    public void onADNeutralButtonClick(String action) {
                        //bouton neutre cliqué, faire qqch ici
                    }
                })
                .show();

# Exemple 2
![alt text](https://github.com/axeldjaha/dialoglibrary/blob/master/Exemple%202.png?raw=true)

        /**
         * On crée la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit et on personnalise les éléments qu'on veut afficher
         * on définit éventuellement un écouteur d'évènement pour les différents boutons du footer
         * et on affiche la boîte de dialogue ainsi créée.
         */
        ADDialog.newInstance(getSupportFragmentManager())
                .setHeaderText("Initialisation")
                .setHeaderTextColor(getResources().getColor(R.color.noir))
                .setBodyText("Les données seront supprimées")
                .setPositiveButtonText("Initialiser")
                .setNegativeButtonText("Annuler")
                .setFooterTextColor(getResources().getColor(R.color.blanc))
                .setDialogBackgroundColor(getResources().getColor(R.color.bleu))
                .setListener(new ADDialogListenerAdapter() {
                    @Override
                    public void onADPositiveButtonClick(String action) {
                        //bouton positif cliqué, faire qqch ici
                    }

                    @Override
                    public void onADNegativeButtonClick(String action) {
                        //bouton négatif cliqué, faire qqch ici
                    }
                })
                .show();

# Exemple 3
![alt text](https://github.com/axeldjaha/dialoglibrary/blob/master/Exemple%203.png?raw=true)

        /**
         * On crée la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit et on personnalise les éléments qu'on veut afficher
         * on définit éventuellement un écouteur d'évènement pour les différents boutons du footer
         * et on affiche la boîte de dialogue ainsi créée.
         */
        ADDialog.newInstance(getSupportFragmentManager())
                .setHeaderText("Attention")
                .setHeaderIcon(getResources().getDrawable(R.drawable.warning))
                .setBodyText("La suppression est irreversible")
                .setPositiveButtonText("Supprimer")
                .setNegativeButtonText("Annuler")
                .setFooterTextColor(getResources().getColor(R.color.bleu))
                .setFooterBackgroundColor(getResources().getColor(R.color.gray_light))
                .setListener(new ADDialogListenerAdapter(){
                    @Override
                    public void onADPositiveButtonClick(String action) {
                        super.onADPositiveButtonClick(action);
                        //bouton positif cliqué, faire qqch ici
                    }

                    @Override
                    public void onADNegativeButtonClick(String action) {
                        super.onADNegativeButtonClick(action);
                        //bouton positif cliqué, faire qqch ici
                    }
                })
                .show();

# Exemple 4
![alt text](https://github.com/axeldjaha/dialoglibrary/blob/master/Exemple%204.png?raw=true)

        /**
         * On crée la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit et on personnalise les éléments qu'on veut afficher
         * et on affiche la boîte de dialogue ainsi créée.
         *
         * ici on a défini aucun un écouteur d'évènement pour les différents boutons du footer,
         * Vous êtes libre de personnaliser la boîte de dialogue comme bon vous semble !
         */
        ADDialog.newInstance(getSupportFragmentManager())
                .setHeaderText("Succès")
                .setBodyText("Message envoyé avec succès")
                .setPositiveButtonText("Ok")
                .show();

# Fonctionnalités

| Méthodes applicables sur ADDialog  | Description |
| --------------------------------- | ----------- |
| newInstance(android.support.v4.app.FragmentManager fragmentManager) | Créer une instance de la boîte de dialogue
| setAction(java.lang.String action) | Définir l'action à exécuter. Différents éléments peuvent ouvrir la boîte de dialogue. L'action permettra alors de savoir les instructions à exécuter lorsqu'on implémente les méthodes de l'interface ADDialogListener. Un élément peut être un Button, un TextView, un EditText ou tout autre widget |
| setBodyBackgroundColor(int colorId) | Définir la couleur de fond du corps |
| setBodyPadding(int left, int top, int right, int bottom) | Définir le padding du corps de la bôite de dialogue |
| setBodyText(java.lang.String bodyText) | Définir le texte à afficher dans le corps de la boîte de dialogue |
| setBodyTextColor(int colorId) | Définir la couleur de texte du corps de la boîte de dialogue |
| setDialogBackgroundColor(int colorId) | Définir la couleur de fond de la boîte de dialogue |
| setDialogCancelable(boolean cancelable) | Définir le comportement de la boîte de dialogue |
| setFooterBackgroundColor(int colorId) | Définir la couleur de fond du pied de la boîte de dialogue |
| setFooterPadding(int left, int top, int right, int bottom) | Définir le padding du pied de la bôite de dialogue |
| setFooterTextColor(int colorId) | Définir la couleur de texte du pied de la boîte de dialogue |
| setHeaderBackgroundColor(int colorId) | Définir la couleur de fond de l'entête |
| setHeaderIcon(android.graphics.drawable.Drawable drawable) | Définir l'icon de l'entête |
| setHeaderPadding(int left, int top, int right, int bottom) | Définir le padding de l'entête de la bôite de dialogue |
| setHeaderText(java.lang.String headerText) | Définir le texte de l'entête |
| setHeaderTextColor(int colorId) | Définir la couleur de texte de l'entête |
| setListener(ADDialogListener listener) | Définir l'écouteur d'évènement pour les boutons du pied de la boîte de dialogue |
| setNegativeButtonText(java.lang.String negativeButtonText) | Définir le texte du bouton négatif de la bôite de dialogue |
| setNeutralButtonText(java.lang.String neutralButtonText) | Définir le texte du bouton neutre de la bôite de dialogue |
| setPositiveButtonText(java.lang.String positiveButtonText) | Définir le texte du bouton positif de la bôite de dialogue |
| show() | Afficher la boîte de dialogue |

# Interface
Pour écouter les boutons du footer et savoir quel bouton a été cliqué par l'utilisateur, implémenter ADDialogListener.

| Méthodes de l'interface ADDialogListener  | Description |
| --------------------------------- | ----------- |
| onADNegativeButtonClick(java.lang.String action) | Appelé lorsque l'utilisateur clique sur le bouton négatif |
| onADNeutralButtonClick(java.lang.String action)  | Appelé lorsque l'utilisateur clique sur le bouton neutre |
| onADPositiveButtonClick(java.lang.String action) | Appelé lorsque l'utilisateur clique sur le bouton positif |

| ADDialogListenerAdapter|
| --------------------------------- |
| Pour implémenter seulement les méthodes de l'interface dont on a besoin, étendre ADDialogListenerAdapter ou créer une classe anonyme de ADDialogListenerAdapter et redéfnir les méthodes désirées |

