---
title: "Использование графических контейнеров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 337057e10e03712aa93b00d9c687374e53f8dd03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="using-graphics-containers"></a>Использование графических контейнеров
Объект <xref:System.Drawing.Graphics> объект предоставляет методы, такие как <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, и <xref:System.Drawing.Graphics.DrawString%2A> для отображения векторных изображений, растровые изображения и текст. Объект <xref:System.Drawing.Graphics> также имеет несколько свойств, которые влияют на качество и ориентацию элементов, которые являются производными. Например свойство режим сглаживания определяет ли применять сглаживание к прямых и кривых линий, а свойство преобразования world влияет положения и поворота элементов, которые являются производными.  
  
 Объект <xref:System.Drawing.Graphics> объект связан с конкретного устройства отображения. При использовании <xref:System.Drawing.Graphics> для рисования в окне <xref:System.Drawing.Graphics> объекта также привязывается к рассматриваемому окну.  
  
 Объект <xref:System.Drawing.Graphics> объект можно рассматривать как контейнер, так как она содержит набор параметров, влияющих на отображение, и привязывается к конкретному устройству. Можно создать вторичный контейнер внутри существующего <xref:System.Drawing.Graphics> путем вызова метода <xref:System.Drawing.Graphics.BeginContainer%2A> , метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="in-this-section"></a>Содержание  
 [Управление состоянием графического объекта](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Описывает способ управления параметрами качества, областью обрезки и преобразования <xref:System.Drawing.Graphics> объекта.  
  
 [Использование вложенных графических контейнеров](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Показано, как использовать контейнеры для контроля состояния <xref:System.Drawing.Graphics> объекта.
