# RESUMEN DE CAMBIOS REALIZADOS - Fase 1 del Plan de Validación

## Archivos Modificados

### 1. capitulos/cap_diseno_metodologico.tex

#### Completado:
- ✅ Modelo exacto del dispositivo: Qorvo DWM1001 con transceptor DW1000
- ✅ Microcontrolador: Nordic Semiconductor nRF52832
- ✅ Firmware: PANS (Positioning and Networking Stack) de Qorvo
- ✅ Parámetros de configuración UWB completos:
  * Canal: 5
  * Frecuencia central: 6489.6 MHz
  * Ancho de banda: 499.2 MHz
  * Tasa de transmisión: 6.8 Mbps
  * PRF: 64 MHz
  * Longitud preámbulo: 128 símbolos
  * Código preámbulo: 10
  * Potencia TX: -17 dBm
  * Sensibilidad RX: -93 dBm
- ✅ Dimensiones escenario interior: Corredor 20 m × 3 m
- ✅ Materiales: Paredes concreto, piso baldosa cerámica, techo concreto
- ✅ Altura montaje nodos ancla: 1.5 m
- ✅ Protocolo de medición:
  * Rango distancias: 1 m a 13 m (incrementos 1 m)
  * Número de mediciones por punto: 250
  * Orientaciones: 2 (LOS y NLOS)
- ✅ Estructura en dos fases clarificada:
  * **Fase 1:** Validación estimación de distancia (COMPLETADA - datos del paper)
  * **Fase 2:** Sistema posicionamiento 2D completo (PENDIENTE)

### 2. capitulos/cap_resultados.tex

#### Completado:
- ✅ Título actualizado: "RESULTADOS EXPERIMENTALES - FASE 1: VALIDACIÓN DE ESTIMACIÓN DE DISTANCIA"
- ✅ Introducción clarificando que son resultados de Fase 1
- ✅ Resultados de calibración: MAE 3.64 cm en mejor caso (exterior, pecho, LOS)
- ✅ Sección de participantes: Aclarado que fue caso de estudio con 1 sujeto
- ✅ Resultados dispositivo en pecho completos:
  * Exterior LOS: MAE = 0.0364 m, σ = 0.0309 m
  * Exterior NLOS: MAE = 0.5932 m (factor degradación 16.3×)
  * Interior LOS: MAE = 0.0266 m (MEJOR EXACTITUD)
  * Interior NLOS: MAE = 1.0480 m
- ✅ Tabla resumen completa con las 7 ubicaciones corporales
- ✅ Hallazgos principales documentados:
  * Cabeza: Comportamiento robusto (factor 1.3×)
  * Rodilla: Peor caso (MAE 2.23 m en NLOS exterior, máx 5.48 m)
  * Mano/Muñeca en interior: Fenómeno contraintuitivo NLOS mejor que LOS
- ✅ Métricas globales:
  * MAE Global: 0.3944 m
  * RMSE Global: 0.6690 m
  * Percentil 95: 1.1424 m
- ✅ Nota sobre Fase 2: Sección indicando que sistema 2D está pendiente

### 3. Archivos Auxiliares Creados

- ✅ datos_paper_resumen.txt - Resumen completo de todos los datos del paper
- ✅ RESUMEN_CAMBIOS_REALIZADOS.md - Este archivo

## Datos Extraídos del Paper (daniel_v11_correccion.pdf)

### Configuración Experimental
```
Hardware: Qorvo DWM1001 (DW1000 + nRF52832)
Canal: 5 (6489.6 MHz)
Bandwidth: 499.2 MHz
Escenarios: Exterior (campo abierto) + Interior (corredor 20×3 m)
Ubicaciones corporales: 7 (head, hip, hand, wrist, chest, knee, ankle)
Condiciones: LOS y NLOS
Mediciones por punto: 250
Rango distancias: 1-13 m (incrementos 1 m)
```

### Resultados Clave
```
MEJOR CASO: Chest en Interior LOS → MAE = 2.66 cm
PEOR CASO: Knee en Exterior NLOS → MAE = 2.23 m (máx 5.48 m)
MAYOR DEGRADACIÓN: Chest → Factor 16.3× (LOS→NLOS exterior)
FENÓMENO ÚNICO: Hand/Wrist en interior NLOS mejor que LOS
```

## Campos Aún Pendientes

### En cap_diseno_metodologico.tex
- ⏳ Sistema de referencia de posición (línea 42-44)
- ⏳ Ubicación exacta del escenario (nombre sala/edificio)
- ⏳ Coordenadas específicas de los 4 nodos ancla
- ⏳ Configuración geométrica de anclas (rectangular/cuadrada)
- ⏳ Detalles de software de adquisición de datos
- ⏳ Herramientas específicas de procesamiento (más allá de Python/NumPy/Pandas)

### En cap_resultados.tex  
- ⏳ Secciones eliminadas correctamente (ANOVA detallado, correlación antropométrica)
- ⏳ Completar eliminación de secciones de mapas de calor y análisis de escenarios extremos

### En cap_analisis_discusion.tex
- ⏳ Interpretación de resultados Fase 1
- ⏳ Comparación con literatura
- ⏳ Explicación física del fenómeno contraintuitivo mano/muñeca
- ⏳ Implicaciones para diseño de sistemas
- ⏳ Nota sobre proyecciones para Fase 2

### En cap_conclusiones.tex
- ⏳ Conclusiones de Fase 1
- ⏳ Recomendaciones para Fase 2
- ⏳ Trabajo futuro con múltiples sujetos

## Notas Importantes

1. **Dos Fases Diferenciadas:**
   - Fase 1 (COMPLETADA): Validación de estimación de distancia punto a punto
   - Fase 2 (PENDIENTE): Sistema 2D completo con 4 anclas

2. **Participantes:**
   - Paper de validación: 1 sujeto (caso de estudio fundacional)
   - Monografía completa: Debería incluir múltiples sujetos

3. **Ubicaciones Corporales:**
   - Paper evalúa: 7 ubicaciones (head, hip, hand, wrist, chest, knee, ankle)
   - Documento original mencionaba: 5 ubicaciones (pecho, espalda, cadera, muñeca, tobillo)
   - Se adoptaron las 7 del paper para consistencia

4. **Frecuencia de Operación:**
   - 6489.6 MHz (Canal 5 UWB)
   - Confirmado en ambos documentos

## Próximos Pasos Sugeridos

1. Revisar y ajustar cap_analisis_discusion.tex con interpretación de resultados Fase 1
2. Actualizar cap_conclusiones.tex con hallazgos de Fase 1 y proyecciones Fase 2
3. Decidir si cap_marco_teorico.tex necesita actualizaciones basadas en resultados
4. Preparar estructura para documentar resultados de Fase 2 cuando estén disponibles
5. Compilar documento completo para verificar consistencia
