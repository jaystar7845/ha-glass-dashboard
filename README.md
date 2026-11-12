# Starline glass Home dashboard for Home Assistant

The dashboard I use every day: frosted glass cards on a blue-green background, a camera switcher, clock, weather, one-tap scenes, rooms, lights and media.
Built with Mushroom cards. Copy it, swap in your own devices, done.

## What you need
- Home Assistant (2024.x or newer, with the "Sections" dashboard layout)
- The **Marketplace** (it used to be called **HACS**, the Home Assistant Community Store): https://hacs.xyz. Older Home Assistant installs still show it as HACS.
- Three cards from the Marketplace: **Mushroom**, **card-mod** and **button-card**

## 1. Install the cards
1. Open **Marketplace** (or **HACS** on older versions) in your sidebar.
2. Search **Mushroom** → open it → **Download**.
3. Do the same for **card-mod** and **button-card**.
4. Refresh your browser (or restart the Home Assistant app).

## 2. Add the clock sensors (for the big clock)
Settings → Devices & services → **Add integration** → **Time & Date** → tick **Time** and **Date**.
This gives you `sensor.time` and `sensor.date`.

## 3. Add the camera switcher (optional)
Settings → Devices & services → **Helpers** → **Create helper** → **Dropdown**.
- Name: `Home camera` (so it becomes `input_select.home_camera`)
- Options: `Camera 1`, `Camera 2`, `Camera 3`

No cameras? Delete the camera section from the YAML (the block with `input_select.home_camera`).

## 4. Make the dashboard
1. Settings → **Dashboards** → **Add dashboard** → **New dashboard from scratch**. Call it Home.
2. Open it → pencil (top right) → three dots → **Raw configuration editor**.
3. Delete what's there, paste in everything from **dashboard.yaml**, and **Save**.

## 5. Swap in your own devices
Every device in the file is a placeholder. Change each one to your own (find your names in Settings → Devices & services → **Entities**):

| In the file | Change to your… |
|---|---|
| `alarm_control_panel.home_alarm` | alarm panel (or delete the Security chip) |
| `sensor.desk_power`, `sensor.fan_power`, `sensor.server_power` | smart plugs with power monitoring |
| `sensor.bedroom_temperature` | a temperature sensor |
| `camera.camera_1/2/3` | cameras |
| `script.good_morning`, `script.good_night`, `script.away_mode`, `script.ambience` | your own scripts (Settings → Automations & scenes → Scripts) |
| `light.lounge_main`, `light.lounge_lamp`, `light.bedroom_light`, `light.kitchen_light`, `light.hallway_light` | lights |
| `media_player.lounge_tv`, `media_player.bedroom_tv` | TVs |
| `weather.forecast_home` | usually already right |

Tip: a card shows "Entity not available" until you swap its name, which makes it easy to spot what's left.

## Want it done for you?
Ready-made dashboards with every room done are in the Starline Smart Living Etsy shop.

Free to use and change. If it helps you, a follow for Starline Smart Living on YouTube or TikTok is appreciated.
