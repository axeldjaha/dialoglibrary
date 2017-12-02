# Avant propos
Les Classes et interfaces de toute librairie 'axeldjaha' commencent toujours par AD, qui signifie Axel Djaha (l'auteur).
# dialoglibrary
Librairie pour interagir avec l'utilisateur dans une boîte de dialogue.
# Gradle
compile 'axeldjaha.library:dialog:1.0'
# Usage: exemple 1
![alt text](https://public.boxcloud.com/api/2.0/internal_files/251685856024/versions/265400118232/representations/png_paged_2048x2048/content/1.png?access_token=1!Ch4gedEeG3ZanMyP7gJTY9mhhQfq2Qz2vMZoryYKnEoS3gciEZEEwbBvlY1iyVA4a7n6tJ_MV7Z3I23wE3mu-TQi4P9euIXx3yvM-992a5D-Kh6GFFEo328ToCVeUGk9955a_yrUw6lKwBfYvG0mCJsUYWmj7rQPKrS5_tnWTkD1OlrjGz5eAs15myzgWKftjpTtl_iz3lVtdoG7aGNVaO2dLy_nmoYsUQaezm0gkivNbKXa1CPUyEeFvKEGL3poKeA8Yg4wCNMYO3mDj7oW1xvo6Ow9ff52KsSEhtR-c0T4XkzxIM7c_hvKUfr7HLqABWSzP1D7SzwUOQjQ_ZP0wnmkwNKnz4R1Ph-I2b3jpHtql6COMfh8kEKRaBx8LunIbvYN_rnJk5ELUjOf&box_client_name=box-content-preview&box_client_version=1.20.2)

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

