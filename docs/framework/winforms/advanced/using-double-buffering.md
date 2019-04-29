---
title: Двойная буферизация графики
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777160"
---
# <a name="using-double-buffering"></a>Двойная буферизация графики
Двойная буферизация графики можно использовать для уменьшения эффекта дрожания изображения в приложениях, которые содержат сложных операций рисования. .NET Framework содержит встроенную поддержку двойной буферизации или вы можете управлять и отображения графики вручную.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Двойная буферизация графики](double-buffered-graphics.md)  
 Появилась двойной буферизации поддержка .NET Framework и описание.  
  
 [Практическое руководство. Уменьшить мерцания изображения посредством двойной буферизации для форм и элементов управления](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Демонстрирует использование поддержки двойной буферизации в .NET Framework по умолчанию.  
  
 [Практическое руководство. Управление буферизацией графики](how-to-manually-manage-buffered-graphics.md)  
 Описывает процессы управления двойной буферизации в приложениях.  
  
 [Практическое руководство. Визуализация буферизированной графики вручную](how-to-manually-render-buffered-graphics.md)  
 Показана Подготовка к просмотру двойная буферизация графики.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Метод Control, который позволяет двойной буферизации.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Предоставляет методы для создания графических буферов.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Предоставляет доступ к контексту буферизованной графики для домена приложения.
