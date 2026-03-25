# Salburua — Guraso elkartearen webgunea

Hugo + gai pertsonal minimoa + [Decap CMS](https://decapcms.org/) (Netlify Identity + Git Gateway) + Netlify argitalpena.

## Lokalki exekutatzea

1. Instalatu [Hugo](https://gohugo.io/installation/) (Extended ez da beharrezkoa gai honetan).
2. Biltegi hau klonatu edo deskargatu.
3. Proiektuaren erroan:

   ```bash
   hugo server
   ```

4. Ireki nabigatzailean `http://localhost:1313/`.

## Proiektuaren egitura

- `config.yaml` — Hugo konfigurazioa (`baseURL`: `https://salburua.mundurat.net/`, hizkuntza `eu`).
- `content/` — Markdown edukia.
- `themes/salburua/` — Kanpoko gairik gabeko gai minimoa (plantillak).
- `static/css/` — Estiloak.
- `static/admin/` — Decap CMS (`/admin/` URLan).
- `static/images/` — Irudiak (`/images/...` bide publikoa).
- `netlify.toml` — Netlify eraikuntza (`hugo` → `public`).

## Netlifyra argitaratzea

1. Sortu [Netlify](https://www.netlify.com/) kontua eta **Add new site** → **Import an existing project**.
2. Konektatu GitHub biltegi hau.
3. Ezarpen lehenetsiak:

   - **Build command:** `hugo`
   - **Publish directory:** `public`

   `netlify.toml` dagoeneko ezartzen ditu balio hauek.

4. Eginda: **Deploy site**. Domeinu pertsonalizatua (`salburua.mundurat.net`) Netlifyn **Domain settings** atalean lotu behar da (DNS erregistroak hornitzailearen arabera).

## CMS saioa (Decap + Netlify Identity)

Administrazioa: `https://zure-gunea.netlify.app/admin/` (edo zure domeinua + `/admin/`).

1. **Identity aktibatu:** Netlify → zure gunea → **Site configuration** → **Identity** → **Enable Identity**.
2. **Erregistroa:** Identity → **Registration** → gomendagarria **Invite only** (gonbidapenak soilik).
3. **Git Gateway:** Identity → **Services** → **Enable Git Gateway** (biltegiarekin lotzen du; lehen aldian baieztapenak eskatu ditzake).
4. **Erabiltzaileak:** Identity → **Invite users** — gonbidatutakoek posta eta pasahitzarekin sartuko dira.

CMS konfigurazioa: `static/admin/config.yml`. Zure biltegiaren adarra ez bada `main`, aldatu `backend.branch` balioa.

## Oharrak

- Gai kanpokorik ez da erabiltzen; guztia `themes/salburua` eta `static/` barruan dago.
- i18n osoa ez dago konfiguratuta; edukia euskaraz dago, eta etorkizunean *Nor gara* orrian gaztelania gehitzea posible da edukiaren arabera, Hugo i18n sistema zabaldu gabe.

## Lizentzia

Proiektuaren edukia eta kodea elkartearen barneko erabilerarako prestatuta dago; lizentzia zehaztu gabe badago, gehitu `LICENSE` fitxategia behar izanez gero.
