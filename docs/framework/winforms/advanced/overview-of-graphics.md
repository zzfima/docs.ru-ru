---
title: Обзор графических возможностей
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: a69bfc2e9983484f90b1b65abd234df2519b503e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523557"
---
# <a name="overview-of-graphics"></a>Обзор графических возможностей
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Представляет интерфейс программирования (API), формирует подсистему операционной системы Microsoft Windows. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] отвечает за отображение информации на экранах и принтерах. Как видно из имени, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] является последователем [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], интерфейса графических устройств, входившего в состав более ранних версий Windows.  
  
## <a name="managed-class-interface"></a>Интерфейс управляемых классов  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API предоставляется через набор классов, развертываемых в виде управляемого кода. Этот набор классов называется *интерфейс управляемых классов* для [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Интерфейс управляемых классов состоит из следующих пространств имен.  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 С помощью интерфейса графических устройств таких как [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], могут отображать данные на экран или на принтер без необходимости думать о деталях каждого конкретного устройства отображения. Программист вызывает методы, предоставляемые классами [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Эти методы, в свою очередь, осуществляют вызовы драйверов определенных устройств. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] изолирует приложение от графического оборудования. Именно такая изоляция дает программистам возможность создавать аппаратно независимые приложения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о графике](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
