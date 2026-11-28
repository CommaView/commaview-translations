---
title: "Presentamos CommaView: transmisión local de la cámara para dispositivos comma"
description: "CommaView es una app de Android para ver la cámara de tu comma en local, con superposiciones al estilo MICI, configuración del entorno, grabaciones y reproducción de viajes."
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma device camera streaming
  - Android app
  - openpilot tools
heroLabel: "Notas del producto"
draft: false
---

CommaView existe porque ver la cámara de tu comma en local debería sentirse como un producto de verdad, no como un montón de scripts pegados a una sesión SSH.

El objetivo es sencillo: emparejar un dispositivo Android con tu comma, transmitir la cámara de carretera en local, mostrar superposiciones de conducción útiles y que la configuración sea aburrida, en el mejor sentido.

## ¿Por qué local primero?

CommaView no intenta ser un panel en la nube. La app habla con tu comma por tu conexión local y mantiene lo esencial cerca del hardware.

Eso importa porque una app que transmite la cámara del comma en local puede ser rápida, fácil de entender y respetuosa con la privacidad. No debería hacer falta una cuenta solo para ver lo que ve tu propio dispositivo.

## Qué hace CommaView

La alfa actual se centra en lo que hace menos molestas las pruebas del día a día:

- transmisión local de la cámara de carretera a Android
- superposiciones al estilo MICI de trayectoria, carriles, estado y supervisión del conductor
- configuración guiada del entorno de ejecución para el servicio `commaviewd` del comma
- grabaciones de viajes y exportación de reproducciones
- versiones de la app y del entorno emparejadas, para que los testers instalen versiones compatibles

## ¿Por qué Android primero?

CommaView es solo para Android porque Android es el destino práctico para este uso: teléfonos, tablets, instalación manual de apps, redes locales y hardware pensado para el coche encajan mejor ahí.

Ese enfoque permite que la app siga siendo precisa en lugar de diluirse para cada plataforma posible.

## Lo que viene

El acceso anticipado de los testers ayudará a pulir la instalación, comprobar la compatibilidad de dispositivos y mejorar la alineación de las superposiciones en vivo en más coches y configuraciones de comma.

Si quieres participar, únete a la lista de acceso anticipado en la página de inicio. Usaremos el blog para notas de versión, novedades para testers y notas técnicas a medida que CommaView crezca.
