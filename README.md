# TestExam_Development
A smaller task to prep for exam in development

-- TODO:
- Homepage where user can view regesterd guest.
- Make sure they can see what the users are regesterd for.
- A guest regeseter with a DB.
- A way to remove guests.
- The DB for the guests and activities.
-- DONE (If u got more thats fine)




## Databasediagram
Siden gjester kan gå på flere arrangementer, og arrangementer kan ha flere gjester får vi en mange-til-mange relasjon på Gjester og Arrangementer.

Derfor har vi en tabell i midten som skal håndere dette kaldt "Registreringer". Her blir en gjest registrert når den melder seg på et arrangement.

Hvis man da skulle hatt hele gjestelisten til ett arrangement basert på arrangementets Id, kunne man kjørt en slik SQL spørring:

```SQL
SELECT 
    Registreringer.Id AS RegistreringId,
    Gjester.Id AS GjestId,
    Gjester.Navn,
    Gjester.Epost,
    Gjester.Telefonnummer
FROM
    Registreringer
JOIN
    Gjester on Registreringer.GjesteId = Gjester.Id
WHERE
    Registreringer.ArrangementId = 1;
```


### Databasediagram:

[![](https://mermaid.ink/img/pako:eNqlUk1PwzAM_SuRz9vUNe36IYTE2IS4IIQ4oV4C9bqyNqm8FgFj_52kH1tXJjiQSJH87Pf8ancHLypGCAFpkYqERB5Jps_NK25LJPb1NR6rHXvAJN2WhJTKRKMha6oiWEqWmFK2EZKtBVtlSMjopLypvXimS13dT9WkTVUTsRWKoJWu3ysioSVylI0ZdsZNz0zJxJHwf0vliZ5xZm5_PLsmNCfVHW_jY6wVjd6deJM_wGWh9JcO0UfMcKWkrPK8c7jvGg4W8EtfEzf2hmhvmF3qoH866D_k51RtkIbovdDcXGw3qTyXmmOmiiO8ECWaR7VGYAQJpTGEJVU4Aj2BXJgQai8RlGttLgK9bIhxJaqs3oehFUI-KZV3TFJVsoZwJbKtjqoi1o3aX_uAEsoY6VpVsoRw6vuzWgXCHbzr2OYTy-K2Z7vcmvmBq7MfGvYms-nUsS3OLdsNPM_ej-CzbmxNPB44vuPYAXcDh8_23w-tC2Q?type=png)](https://mermaid.live/edit#pako:eNqlUk1PwzAM_SuRz9vUNe36IYTE2IS4IIQ4oV4C9bqyNqm8FgFj_52kH1tXJjiQSJH87Pf8ancHLypGCAFpkYqERB5Jps_NK25LJPb1NR6rHXvAJN2WhJTKRKMha6oiWEqWmFK2EZKtBVtlSMjopLypvXimS13dT9WkTVUTsRWKoJWu3ysioSVylI0ZdsZNz0zJxJHwf0vliZ5xZm5_PLsmNCfVHW_jY6wVjd6deJM_wGWh9JcO0UfMcKWkrPK8c7jvGg4W8EtfEzf2hmhvmF3qoH866D_k51RtkIbovdDcXGw3qTyXmmOmiiO8ECWaR7VGYAQJpTGEJVU4Aj2BXJgQai8RlGttLgK9bIhxJaqs3oehFUI-KZV3TFJVsoZwJbKtjqoi1o3aX_uAEsoY6VpVsoRw6vuzWgXCHbzr2OYTy-K2Z7vcmvmBq7MfGvYms-nUsS3OLdsNPM_ej-CzbmxNPB44vuPYAXcDh8_23w-tC2Q)