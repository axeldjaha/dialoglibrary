# Avant propos
Les Classes et interfaces de toute librairie 'axeldjaha' commencent toujours par AD, qui signifie Axel Djaha (l'auteur).
# dialoglibrary
Librairie pour interagir avec l'utilisateur dans une boîte de dialogue.
# Gradle
compile 'axeldjaha.library:dialog:1.0'
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
        ADDialog.newInstance(DialogActivity.this.getSupportFragmentManager())
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
        ADDialog.newInstance(DialogActivity.this.getSupportFragmentManager())
                .setHeaderText("Succès")
                .setBodyText("Message envoyé avec succès")
                .setPositiveButtonText("Ok")
                .show();

