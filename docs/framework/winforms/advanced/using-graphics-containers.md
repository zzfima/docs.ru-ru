---
title: Использование графических контейнеров
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: 8755a95434d3fed06a55cfca0f71d86e5521cb39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525025"
---
# <a name="using-graphics-containers"></a>Использование графических контейнеров
Объект <xref:System.Drawing.Graphics> объект предоставляет методы, такие как <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, и <xref:System.Drawing.Graphics.DrawString%2A> для отображения векторных изображений, растровые изображения и текст. Объект <xref:System.Drawing.Graphics> также имеет несколько свойств, которые влияют на качество и ориентацию элементов, которые являются производными. Например свойство режим сглаживания определяет ли применять сглаживание к прямых и кривых линий, а свойство преобразования world влияет положения и поворота элементов, которые являются производными.  
  
 Объект <xref:System.Drawing.Graphics> объект связан с конкретного устройства отображения. При использовании <xref:System.Drawing.Graphics> для рисования в окне <xref:System.Drawing.Graphics> объекта также привязывается к рассматриваемому окну.  
  
 Объект <xref:System.Drawing.Graphics> объект можно рассматривать как контейнер, так как она содержит набор параметров, влияющих на отображение, и привязывается к конкретному устройству. Можно создать вторичный контейнер внутри существующего <xref:System.Drawing.Graphics> путем вызова метода <xref:System.Drawing.Graphics.BeginContainer%2A> , метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Управление состоянием графического объекта](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Описывает способ управления параметрами качества, областью обрезки и преобразования <xref:System.Drawing.Graphics> объекта.  
  
 [Использование вложенных графических контейнеров](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Показано, как использовать контейнеры для контроля состояния <xref:System.Drawing.Graphics> объекта.
