# CRO Calc — Simulador de Staking de CRO 🇲🇽

Simulador de intereses de staking de **CRO** (Crypto.com) pensado para México:
las transacciones se registran en **USD** y los resultados se muestran también en **pesos mexicanos (MXN)**.

## Cómo usarlo

Abre `index.html` en cualquier navegador. No requiere instalación, servidor ni dependencias.
También puedes publicarlo gratis con GitHub Pages (Settings → Pages → branch `main`).

## Qué hace

- **Precios en vivo**: CRO/USD, CRO/MXN y tipo de cambio USD/MXN, actualizados automáticamente cada 60 segundos
  (fuente principal: CoinGecko; respaldo: API pública del Exchange de Crypto.com + open.er-api.com).
- **APY editable**: por defecto **5.24% anual** (la tasa actual de staking); cámbiala cuando Crypto.com la ajuste y se recalcula todo.
- **Simulador de retorno**: ingresa un monto en USD, MXN o CRO y ve la ganancia en CRO/USD/MXN a 1 día,
  1 semana, 1 mes, 6 meses, 1, 2 y 5 años, con interés simple o compuesto (reinversión diaria).
- **"¿Cuánto necesito para vivir de esto?"**: ingresa tu gasto mensual en MXN y te dice cuánto capital
  necesitas en staking (en CRO, USD y MXN), cuánto ya tienes y cuánto te falta.
- **Registro de depósitos**: fecha, monto en USD, precio de CRO al comprar y CRO recibidos
  (los dos últimos se autocompletan con el precio actual). Calcula valor actual, pérdida/ganancia,
  costo promedio y **recompensas acumuladas estimadas** desde la fecha de cada depósito.
- **Tus datos son tuyos**: todo se guarda en el `localStorage` de tu navegador. Exporta CSV o respaldo JSON
  e impórtalo en otro dispositivo. Nada se envía a ningún servidor.

## Sobre la API privada de Crypto.com (tu balance real)

La app usa solo APIs **públicas** de precios. La API privada de Crypto.com (para leer tu balance y
transacciones reales) requiere una **API key + secret con firma HMAC**, y ponerla en una página web
expondría tus llaves a cualquiera que abra la página. Por eso no está integrada aquí.

Si quieres esa integración, la forma segura es un pequeño backend/proxy (por ejemplo un Cloudflare Worker
o un script local) que guarde las llaves y firme las peticiones — se puede agregar como siguiente paso.
**Nunca pegues tu API secret en una página web ni lo compartas en un chat.** Mientras tanto, registrar tus
depósitos manualmente en la app te da el mismo resultado.

## Nota

Herramienta de estimación, no asesoría financiera. Las recompensas de staking se pagan en CRO:
su valor en pesos depende del precio de CRO y del tipo de cambio, que varían todos los días.
