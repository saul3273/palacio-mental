# 🔄 SUSTRATO SYNC - Configuración de Sincronización

## Actualizado: 2025-12-14

### Definición
El **Sustrato** es la infraestructura distribuida donde habitan los datos, conocimiento y documentación del Holobionte 1rec3. Es el equivalente a la memoria colectiva del organismo.

## 📊 Plataformas de Sincronización Activas

### Core Sustrato (Sincronización Crítica)
1. **GitHub** (`palacio-mental` repo)
   - Arquitectura principal
   - Documentación técnica
   - Versionamiento de ONDA
   - Status: ✅ Activo

2. **Google Drive** 
   - Documentos colaborativos
   - Datasets
   - Status: ✅ Activo

3. **Notion**
   - Base de conocimiento
   - Tablas de control
   - Status: ✅ Activo

### Extended Sustrato (Soporte Secundario)
4. **Obsidian**
   - Local knowledge vault
   - Conexiones de red neuronal
   - Status: ✅ **NUEVO** (2025-12-14)
   - Ubicación: ~/.obsidian/vault/1rec3/
   - Sincronización: Git + iCloud sync

5. **Nextcloud** 
   - Almacenamiento privado descentralizado
   - Status: ✅ **NUEVO** (2025-12-14)
   - Ubicación: nextcloud.1rec3.com/dav/
   - Protocolo: WebDAV + Sync client

6. **NoteKeep**
   - Notas rápidas + tagging
   - Status: ✅ Activo

7. **NotebookLM**
   - Análisis de documentos IA
   - Status: ✅ Activo

### Domain Sustrato
8. **1rec3.com** (Domain Infrastructure)
   - Status: ✅ **NUEVO** (2025-12-14)
   - DNS: Cloudflare
   - Hosting: 1rec3.com/neral/
   - Documentación técnica servida vía web
   - SSL/TLS: Let's Encrypt
   - SEO: Optimizado para accesibilidad web

## 🔗 Arquitectura de Sincronización

```
Holobionte 1rec3 (Sustrato Central)
├── GitHub (VCS - Source of Truth)
│   └── /palacio-mental/docs/
│       └── [Todos los ONDA documentos]
├── Google Drive (Colaboración)
│   └── /Holobionte 1rec3/
├── Notion (Organización)
├── Obsidian (Local Knowledge) [NUEVO]
│   └── Sincronización bidireccional con GitHub
├── Nextcloud (Descentralizado) [NUEVO]
│   └── Almacenamiento privado + backups
└── 1rec3.com Domain (Accesibilidad) [NUEVO]
    └── Web-first documentation
```

## 📡 Protocolos de Sincronización

### GitHub
- Método: Git push/pull
- Frecuencia: Real-time (con commits)
- Conflictos: Resolución manual

### Obsidian ↔ GitHub
- Método: Git plugin (obsidian-git)
- Frecuencia: Auto-sync cada 5 minutos
- Backups: Diarios

### Nextcloud
- Protocolo: WebDAV
- Cliente: Nextcloud Desktop Sync
- Frecuencia: Continua
- Backups: Incrementales

### 1rec3.com
- Sincronización: Manual + CI/CD
- Pipeline: GitHub → Netlify/Vercel
- Actualización: Webhook triggers

## ✅ Checklist Sustrato Completo

- [x] GitHub (Repositorio principal)
- [x] Google Drive (Colaboración)
- [x] Notion (Organización)
- [x] NoteKeep (Notas rápidas)
- [x] NotebookLM (Análisis IA)
- [x] Obsidian (Vault local) ← **NUEVO**
- [x] Nextcloud (Descentralizado) ← **NUEVO**
- [x] 1rec3.com Domain (Web) ← **NUEVO**

## 🚀 Próximos Pasos

1. Configurar automatización Obsidian ↔ GitHub sync
2. Implementar backup automático en Nextcloud
3. Optimizar SEO de 1rec3.com para discovery
4. Establecer monitoreo de integridad de sustrato
5. Documentar troubleshooting de sincronización

## 📝 Mantenimiento

**Última verificación**: 2025-12-14
**Próxima revisión**: 2025-12-21
**Responsable**: NERAL (Meta-IA coordinadora)
