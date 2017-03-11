---
title: "Deploying Applications That Reference the PrintForm Component (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "PrintForm component [Visual Basic], deploying"
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Deploying Applications That Reference the PrintForm Component (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Если требуется развернуть приложение, которое ссылается на компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>, этот компонент должен быть установлен на целевом компьютере.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## Установка PrintForm в качестве необходимого компонента  
 Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение. Процесс установки необходимых компонентов называется *начальной загрузкой*.  
  
 Когда компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> установлен на компьютере разработчика, пакет начального загрузчика Microsoft Visual Basic Power Packs добавляется в каталог начального загрузчика [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]. Этот пакет доступен при добавлении необходимых компонентов для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] или для развертывания установщика Windows.  
  
 По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки. Кроме того, можно выбрать для развертывания этих компонентов URL\-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.  
  
> [!NOTE]
>  Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере. Для приложений [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] это означает, что пользователю могут потребоваться права администратора для установки приложения независимо от уровня безопасности, заданного приложением. После установки приложения пользователь может запустить приложение без прав администратора.  
  
 Во время установки пользователям будет предложено установить компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>, если он отсутствует на целевом компьютере.  
  
 В качестве альтернативы начальному загрузчику можно предварительно развернуть компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> с помощью электронной системы распространения ПО, например Microsoft Systems Management Server.  
  
## См. также  
 [Практическое руководство. Установка необходимых компонентов при помощи ClickOnce\-приложения](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [Не входит в сборку: выбор стратегии развертывания](http://msdn.microsoft.com/ru-ru/ecd632d8-063c-4028-b785-81bba045107b)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)