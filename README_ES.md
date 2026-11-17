# ComfyUI-Qwen21-IdentityVault-V6 — extensión independiente

**Nombre propuesto para repositorio GitHub:** `ComfyUI-Qwen21-IdentityVault-V6` (no se ha publicado).

Esta es una **instalación nueva** y NO una actualización de `ComfyUI-QwenImage21-RefMod-Manager`. Las clases Python, ruta HTTP para actualizar, carpeta de perfiles y JavaScript son propios de la V6.

## Instalación
1. Extrae únicamente la carpeta `ComfyUI-Qwen21-IdentityVault-V6` dentro de `ComfyUI/custom_nodes/`.
2. Reinicia ComfyUI y recarga la interfaz con Ctrl+Shift+R.
3. Abre `01_CREAR_IDENTITYVAULT_8_FOTOS_V6.json` y crea el perfil con hasta 8 imágenes (se guardará en `ComfyUI/input/qwen_identity_vault_v6/`).
4. Abre `02_GENERAR_TEXTO_A_IMAGEN_IDENTITYVAULT_V6.json`. El nodo `QWEN IDENTITYVAULT V6 | LOADER + REFRESH` debe mostrar un botón de acción **Actualizar RefMods**. Selecciona el perfil y ejecuta.

## Perfiles previos
El selector busca perfiles guardados en `ComfyUI/input/qwen_refmods_v3`, `qwen_refmods_v4`, `qwen_refmods_v5` y en el nuevo `qwen_identity_vault_v6`. No migra ni altera esos archivos.

## Alcance real
Es un prototipo que reutiliza imágenes RGB y latentes VAE, NO un vector de identidad fusionada entrenado. Puede producir collages: no está resuelto el defecto de condicionamiento multirreferencia. La corrección del tokenizer usa `images=[]` para el negativo. No se ha probado en GPU ni en tu interfaz.

## Si no aparece el botón
Confirma que `ComfyUI/custom_nodes/ComfyUI-Qwen21-IdentityVault-V6/web/refresh.js` existe y que la extensión `QwenIdentityVaultV6.RefreshButton` aparece en las extensiones del navegador. El botón es provisto por JavaScript de la extensión, no por un widget Python nativo.
