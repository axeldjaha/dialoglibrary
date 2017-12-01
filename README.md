# Avant propos
Les Classes et interfaces de toute librairie 'axeldjaha' commencent toujours par AD, qui signifie Axel Djaha (l'auteur).
# dialoglibrary
Librairie pour afficher des messages dans une boîte de dialogue.
# Gradle
compile 'axeldjaha.library:dialog:1.0'
# Usage: exemple 1

        /**
         * On construit la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit le titre et/ou le message à afficher,
         * on définit éventuellement le texte des différents boutons à afficher
         * on définit éventuellement un écouteur d'évènement pour les différents boutons
         * et on affiche la boîte de dialogue ainsi créée.
         */
        ADDialog.buildDialog(getSupportFragmentManager())
                .setTitle("Que faire ?")
                .setMessage("Choisir l'action à exécuter")
                .setPositiveButtonText("Renommer")
                .setNegativeButtonText("Supprimer")
                .setNeutralButtonText("Annuler")
                .setListener(new ADDialogListenerAdapter(){
                    @Override
                    public void onADPositiveActionPerformed(String action) {
                        super.onADPositiveActionPerformed(action);
                        //l'utilisateur a cliqué sur Renommer, faire qqch ici
                    }

                    @Override
                    public void onADNegativeActionPerformed(String action) {
                        super.onADNegativeActionPerformed(action);
                        //l'utilisateur a cliqué sur Supprimer, faire qqch ici
                    }

                    @Override
                    public void onADNeutralActionPerformed(String action) {
                        super.onADNeutralActionPerformed(action);
                        //l'utilisateur a cliqué sur Annuler, faire qqch ici
                    }
                })
                .show();

# Usage: exemple 2

        /**
         * On construit la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit le titre et/ou le message à afficher,
         * on définit éventuellement le texte des différents boutons à afficher
         * on définit éventuellement un écouteur d'évènement pour les différents boutons
         * et on affiche la boîte de dialogue ainsi créée.
         */
        ADDialog.buildDialog(getSupportFragmentManager())
                .setTitle("Convertir en pdf ?")
                .setPositiveButtonText("Oui")
                .setNegativeButtonText("Non")
                .setListener(new ADDialogListenerAdapter(){
                    @Override
                    public void onADPositiveActionPerformed(String action) {
                        super.onADPositiveActionPerformed(action);
                        //l'utilisateur a cliqué sur Oui, faire qqch ici
                    }

                    @Override
                    public void onADNegativeActionPerformed(String action) {
                        super.onADNegativeActionPerformed(action);
                        //l'utilisateur a cliqué sur Non, faire qqch ici
                    }
                })
                .show();

