# Smart Charging Dashboard

Modern Home Assistant-dashboard voor **Audi e-tron**, **Easee**, **EV Smart Charging** en **Nord Pool**.

## Inhoud

- Grote Audi SoC-kaart met dynamische statuskleur
- EV Smart Charging-status
- Klaar-om-tijd en slimme laadschakelaar
- Huidige en volgende stroomprijs
- Easee sessie-energie, laadstroom, spanning en verbinding
- Grote knoppen voor **Nu laden**, **Stoppen** en **Slim laden**
- Audi-bediening voor vergrendelen, veilig ontgrendelen, voorverwarmen en verversen
- Compacte antraciete ApexCharts-prijsgrafiek

## Vereiste HACS-kaarten

Installeer deze frontend-componenten via HACS:

- Mushroom Cards
- Button Card
- ApexCharts Card
- card-mod

Herlaad daarna de browser volledig.

## Installeren

1. Open [`dashboard/dashboard.yaml`](dashboard/dashboard.yaml).
2. Kopieer de volledige inhoud.
3. Maak in Home Assistant een nieuw dashboard via **Instellingen → Dashboards → Dashboard toevoegen**.
4. Open het nieuwe dashboard.
5. Kies **Bewerken → drie puntjes → Ruwe configuratie-editor**.
6. Vervang de bestaande inhoud door de YAML uit dit project.
7. Sla op en vernieuw de pagina.

## Gebruikte entiteiten

```yaml
sensor.audi_e_tron_sportback_state_of_charge
sensor.audi_e_tron_sportback_target_state_of_charge
sensor.ev_smart_charging_status
switch.ev_smart_charging_smart_charging_activated
select.ev_smart_charging_charge_completion_time
sensor.ev_smart_charging_price
sensor.nord_pool_nl_volgende_prijs
button.ev_smart_charging_manually_start_charging
button.ev_smart_charging_manually_stop_charging
sensor.links_sessie_energie
sensor.links_laadstroom
sensor.links_stroom
sensor.links_voltage
binary_sensor.links_online
lock.audi_e_tron_sportback_door_lock
switch.audi_e_tron_sportback_preheater
```

Wanneer een entiteit bij jou anders heet, vervang je alleen die entity-id in `dashboard/dashboard.yaml`.

## Opmerking over de prijsgrafiek

De grafiek gebruikt het attribuut `raw_two_days` van:

```yaml
sensor.ev_smart_charging_charging
```

De waarden worden automatisch van EUR/MWh naar EUR/kWh omgerekend wanneer dat nodig is.

## Versie

`v0.1.0` – eerste werkende Audi-stijl dashboardversie.
