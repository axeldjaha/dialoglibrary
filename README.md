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
         * on définit éventuellement un écouteur d'évènement pour les défférents boutons
         * et on affiche la boîte de dialogue ainsi créée.
         *
         * Ici, le titre est utilisé comme le contenu du message à afficher.
         * Vous êtes libre de construire la boîte de dialogue comme vous le voulez!
         */
        ADDialog.buildDialog(getSupportFragmentManager())
                .setTitle("Supprimer ?")
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

# Usage: exemple 3

        /**
         * On construit la boîte de dialogue avec le fragmentManager d'une AppCompactActivity,
         * on définit le titre et/ou le message à afficher,
         * on définit éventuellement le texte des différents boutons à afficher
         * on définit éventuellement un écouteur d'évènement pour les défférents boutons
         * et on affiche la boîte de dialogue ainsi créée.
         *
         * Ici, on n'a pas défini un écouteur d'évènement
         * Vous êtes libre de construire la boîte de dialogue selon votre logique!
         */
        ADDialog.buildDialog(getSupportFragmentManager())
                .setTitle("Succès")
                .setMessage("Message envoyé avec succès")
                .setPositiveButtonText("Ok")
                .show();

