---
title: "Двойная буферизация графики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d83846dcded620b74f7d276fd241a302cce1b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-double-buffering"></a>Двойная буферизация графики
Двойная буферизация графики можно использовать для уменьшения мерцания в приложениях, которые содержат сложных операций рисования. Платформа .NET Framework содержит встроенную поддержку двойной буферизации или можно управлять и отображения графики вручную.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Двойная буферизация графики](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Вводит двойной буферизации поддержки .NET Framework и описание.  
  
 [Практическое руководство. Уменьшение эффекта мерцания изображения посредством двойной буферизации для форм и элементов управления](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Демонстрирует использование поддержки двойной буферизации в .NET Framework по умолчанию.  
  
 [Практическое руководство. Управление буферизацией графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Показано, как управлять двойной буферизации в приложениях.  
  
 [Практическое руководство. Прорисовка буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Описание способа отображения двойная буферизация графики.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Метод управления, позволяющий двойной буферизации.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Предоставляет методы для создания графических буферов.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Предоставляет доступ к контексту буферизованной графики для домена приложения.
