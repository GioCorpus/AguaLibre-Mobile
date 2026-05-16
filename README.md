Estructura del Proyecto AguaLibre Mobile:

AguaLibre Mobile es la aplicación móvil complementaria al sistema AguaLibreOS-for-the-Dron. Está diseñada para residentes de Mexicali y operadores de la flota, permitiendo solicitudes de entrega de garrafones de agua, seguimiento en tiempo real, gestión de flota y monitoreo. La aplicación prioriza usabilidad en entornos móviles, conectividad intermitente (común en colonias), bajo consumo de datos y compatibilidad con dispositivos Android e iOS.
Objetivos Principales

Permitir a usuarios finales solicitar entregas de agua de forma sencilla y rastrear drones en tiempo real.
Proporcionar herramientas a operadores para supervisar la flota, rutas y estado de entregas.
Integración segura con el backend de AguaLibreOS (API REST/WebSocket/MAVLink gateway).
Cumplimiento de políticas de Google Play y Apple App Store, especialmente en manejo de ubicación, privacidad y seguridad (drones).
Soporte offline parcial y optimización para redes móviles en Mexicali.

Tecnologías Recomendadas (2026)

Framework principal: Flutter (recomendado por su rendimiento superior en aplicaciones con mapas en tiempo real, animaciones fluidas y consistencia UI entre plataformas). Alternativa: React Native si se prefiere un equipo con fuerte experiencia en JavaScript.
Backend: Integración con API existente de AguaLibreOS (Rust/Node.js).
Mapas y tracking: Google Maps o Mapbox (con soporte offline).
Autenticación: Firebase Auth o Auth0.
Notificaciones: Firebase Cloud Messaging (FCM) / APNs.
Estado en tiempo real: WebSockets o Supabase/Firebase Realtime.
Almacenamiento local: Hive (Flutter) o SQLite.

Estructura de Directorios Recomendada

AguaLibre-Mobile/
├── .github/                    # Workflows CI/CD
├── android/                    # Configuración nativa Android
├── ios/                        # Configuración nativa iOS
├── lib/                        # Código fuente principal (Flutter)
│   ├── core/                   # Configuración, temas, constantes, utils
│   ├── features/
│   │   ├── auth/               # Login, registro, perfiles
│   │   ├── home/               # Dashboard principal
│   │   ├── request/            # Solicitud de entrega (dirección, cantidad, horario)
│   │   ├── tracking/           # Mapa en tiempo real, estado del dron
│   │   ├── history/            # Historial de entregas y pagos
│   │   ├── operator/           # Panel operador (flota, rutas, alertas) - rol protegido
│   │   └── profile/            # Configuración y soporte
│   ├── shared/                 # Widgets, modelos, servicios compartidos
│   ├── services/               # API, location, notifications, WebSocket
│   └── utils/                  # Helpers, offline management
├── assets/                     # Imágenes, icons, mapas offline
├── test/                       # Pruebas unitarias e integración
├── docs/                       # Documentación, guías de publicación
├── pubspec.yaml                # Dependencias
├── firebase.json               # Configuración Firebase (opcional)
└── README.md, LICENSE

Funcionalidades Clave
Para Usuarios Residentes:

Registro y autenticación (teléfono/INE).
Solicitud rápida de garrafones (dirección GPS o manual, cantidad, preferencia horaria).
Seguimiento en tiempo real del dron (mapa, ETA, vista de cámara si aplica).
Historial de entregas y recibos.
Pagos integrados (tarjetas, SPEI, wallets).
Notificaciones push y chat de soporte.

Para Operadores/Admin:

Vista de flota completa y estado de drones.
Asignación manual/automática de entregas.
Alertas de seguridad y clima.
Reportes analíticos (entregas, eficiencia energética).

Características Técnicas:

Modo offline (solicitudes en cola).
Geofencing para zonas autorizadas en Mexicali.
Alta seguridad: cifrado, permisos mínimos de ubicación y cámara.
Soporte multilingüe (español principal, inglés).

Pasos para Publicación en Tiendas

Cuentas de Desarrollador:
Google Play: Pago único de $25 USD.
Apple Developer Program: $99 USD anual.

Requisitos Específicos:
Política de privacidad clara (ubicación solo para entregas).
Cumplir regulaciones mexicanas y AFAC para aplicaciones relacionadas con drones.
Pruebas exhaustivas en dispositivos reales (incluyendo condiciones de calor y polvo).

Proceso:
Generar builds (AAB para Android, IPA para iOS).
Revisión de tiendas (Google: horas/días; Apple: 1-7 días).
Monitoreo post-lanzamiento y actualizaciones frecuentes.


