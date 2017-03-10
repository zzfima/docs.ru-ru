---
title: "Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Power Pack - пакеты, развертывание"
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Если требуется развернуть приложение, ссылающееся на элементы управления пакетов Power Packs \(<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\), необходимо установить эти элементы управления на конечном компьютере.  
  
## Установка элементов управления пакетов Power Packs в качестве необходимых компонентов  
 Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение.  Процесс установки необходимых компонентов также называется *начальной загрузкой*.  
  
 Когда [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] установлен на компьютере разработчика, в каталог загрузчика [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] добавляется пакет загрузчика Power Packs.  После этого пакет можно будет использовать при добавлении компонентов, необходимых для развертывания [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] или установщика Windows.  
  
 По умолчанию компоненты начальной загрузки развертываются с того же веб\-узла, что и пакет установки.  Как вариант можно указать для развертывания этих компонентов URL\-адрес или общую папку, откуда пользователь сможет загрузить их при необходимости.  
  
> [!NOTE]
>  Чтобы установить на компьютере компоненты начальной загрузки, пользователю могут потребоваться права администратора или схожие разрешения пользователя.  В случае с приложениями [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] это означает, что пользователю могут потребоваться права администратора для установки приложения, независимо от уровня безопасности, заданного приложением.  После установки приложения пользователь может запускать его уже без прав администратора.  
  
 Если на конечном компьютере не установлены элементы управления пакетами Power Packs, то во время установки от пользователя может потребоваться установить их.  
  
 Как вариант, вместо начальной загрузки можно предварительно развернуть элементы управления пакетов Power Packs с помощью электронной системы распространения программного обеспечения \(например, с помощью Microsoft Systems Management Server\).  
  
## См. также  
 [How to: Install Prerequisites in Windows Installer Deployment](http://msdn.microsoft.com/ru-ru/653fc868-2486-429c-b75e-2f9d0c7f6619)   
 [Практическое руководство. Установка необходимых компонентов при помощи ClickOnce\-приложения](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [Выбор стратегии развертывания](http://msdn.microsoft.com/ru-ru/ecd632d8-063c-4028-b785-81bba045107b)   
 [Элементы управления Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)