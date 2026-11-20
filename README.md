# eagler-admin

Panel de administración web del server **Eagler Bros** (Fabric 26.2 + Velocity + EaglerX), servido desde GitHub Pages.

La página es **solo frontend**: habla con la API del panel que corre en la PC del server (`panel/mod_panel.py`, puerto 5555, expuesto por túnel cloudflared). La URL vigente del túnel vive en `config.js`; como el quick tunnel de trycloudflare rota en cada arranque, en el server se corre `ACTUALIZAR-URL-PANEL.cmd` para republicarla.

La clave admin (`panel.key`) **no** está en este repo: la guarda el administrador en su navegador (localStorage) y viaja en el header `X-Panel-Key`.

Qué se puede hacer desde la página:
- Estado del server, puertos, servicios Windows y túneles (con reinicio de Fabric/Velocity y servicios).
- Editar `server.properties` y `velocity.toml` (lista blanca de keys, backup automático antes de escribir).
- Whitelist/bans en vivo vía RCON, consola RCON, rangos LuckPerms, control del bot y su personalidad, y logs.
