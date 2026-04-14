# SIGPRA - Prototipo Swing (Proyecto Integrador)

Repositorio del prototipo de gestion de practicas academicas (desktop Java Swing + Oracle).

## URL de entrega (GitHub Publico)
Pega aqui la URL final de tu repo cuando lo publiques:

`https://github.com/<tu-usuario>/PROYECTO_VISTAS_NETBEANS`

## Contenido principal
- `src/main/java`: codigo fuente Java (UI, DAO, modelos, sesion).
- `src/main/resources`: recursos (`db.properties`, branding/logos).
- `docs/`: documentacion organizada para entrega.
  - `docs/01_codigo_documentado/CODIGO_DOCUMENTADO.md`
  - `docs/02_base_datos/bd/` (scripts SQL + version limpia de tablas/usuarios)
  - `docs/03_ui/WIREFRAME_VISTAS.md`

## Requisitos
- JDK 17+ (probado con JDK 23).
- Oracle XE (servicio `XE`).
- Esquema/app user: `PRACTICAS_APP`.

## Configuracion de BD (app)
Archivo: `src/main/resources/db.properties`

Valores por defecto:
- `db.url=jdbc:oracle:thin:@localhost:1521/XE`
- `db.user=PRACTICAS_APP`
- `db.password=Practicas2026`

## Instalacion BD (SQL*Plus)
Desde carpeta `docs/02_base_datos/bd`:

```sql
@00_instalar_bd.sql
```

Ese script ejecuta:
- `01_crear_esquema_oracle.sql`
- `02_datos_iniciales.sql`
- `04_ajustes_reunion_20260310.sql`
- `05_ajuste_roles_video_20260310.sql`

## Usuarios semilla cargados
En `02_datos_iniciales.sql` se insertan usuarios con `hash_password = 'HASH_TEMP_123'`:
- `carlos.ramirez@universidad.edu.co` (DIRECTOR)
- `laura.perez@universidad.edu.co` (TUTOR_ACADEMICO)
- `andres.gomez@universidad.edu.co` (ESTUDIANTE)
- `sofia.martinez@universidad.edu.co` (ESTUDIANTE)
- `diana.lopez@universidad.edu.co` (TUTOR_ACADEMICO)
- `paula.suarez@universidad.edu.co` (DIRECTOR)
- `marta.ruiz@sanjose.edu.co` (ASESOR_PEDAGOGICO)
- `luis.parra@horizonte.edu.co` (ASESOR_PEDAGOGICO)

Nota: el login Swing usa roles `ESTUDIANTE`, `DOCENTE`, `DIRECTOR`.

## Ejecucion local
Clase launcher:
- `co.udi.integrador.ui.launchers.AbrirMenuVistas`

Desde NetBeans:
1. Open Project.
2. Seleccionar `PROYECTO_VISTAS_NETBEANS`.
3. Run File sobre `AbrirMenuVistas`.

## Cambios visuales recientes
- Regla de logos:
  - Inicio/Login usa `logo2`.
  - Resto de vistas usa `logo`.
- Mejora de nitidez en render/escalado de logos.
