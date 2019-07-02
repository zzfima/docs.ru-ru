---
title: Обзор графических возможностей
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505318"
---
# <a name="overview-of-graphics"></a>Обзор графических возможностей
GDI + — прикладной программный интерфейс (API), формирует подсистему операционной системы Microsoft Windows. GDI + отвечает за отображение информации на экранах и принтерах. Как предполагает имя, GDI + является преемником GDI, интерфейса графических устройств, в состав более ранних версиях Windows.  
  
## <a name="managed-class-interface"></a>Интерфейс управляемых классов  
 GDI + API предоставляется через набор классов, развертываемых как управляемый код. Этот набор классов называется *интерфейс управляемых классов* в GDI +. Интерфейс управляемых классов состоит из следующих пространств имен.  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 С помощью интерфейса графических устройств, таких как GDI + могут отображать данные на экран или принтер без необходимости думать о деталях конкретного устройства отображения. Программист вызывает методы, предоставляемые классами GDI +. Эти методы, в свою очередь, осуществляют вызовы драйверов определенных устройств. GDI + изолирует приложение от графического оборудования. Это такая изоляция дает программистам возможность создавать аппаратно независимые приложения.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о графике](graphics-overview-windows-forms.md)
