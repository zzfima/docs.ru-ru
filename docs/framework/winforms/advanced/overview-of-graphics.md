---
title: Обзор графических возможностей
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: a95086645771de61cfc859e34b225992bc16eac9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641350"
---
# <a name="overview-of-graphics"></a>Обзор графических возможностей
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] — прикладной программный интерфейс (API), формирует подсистему операционной системы Microsoft Windows. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] отвечает за отображение информации на экранах и принтерах. Как видно из имени, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] является последователем [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], интерфейса графических устройств, входившего в состав более ранних версий Windows.  
  
## <a name="managed-class-interface"></a>Интерфейс управляемых классов  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API предоставляется через набор классов, развертываемых как управляемый код. Этот набор классов называется *интерфейс управляемых классов* для [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Интерфейс управляемых классов состоит из следующих пространств имен.  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 С помощью интерфейса графических устройств таких как [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно отображать данные на экран или принтер без необходимости думать о деталях конкретного устройства отображения. Программист вызывает методы, предоставляемые классами [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Эти методы, в свою очередь, осуществляют вызовы драйверов определенных устройств. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] изолирует приложение от графического оборудования. Это такая изоляция дает программистам возможность создавать аппаратно независимые приложения.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о графике](graphics-overview-windows-forms.md)
