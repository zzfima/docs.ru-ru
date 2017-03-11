---
title: "Объекты (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объекты [Visual Basic]"
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Объекты (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В этом разделе перечислены ссылки на другие разделы, в которых описаны объекты среды выполнения Visual Basic и их процедуры, свойства и события.  
  
## Объекты среды выполнения Visual Basic  
  
|||  
|-|-|  
|<xref:Microsoft.VisualBasic.Collection>|Предоставляет удобный способ просмотра группы связанных элементов как единого объекта.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|Содержит сведения об ошибках времени выполнения.|  
|Объект `My.Application` состоит из следующих классов:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> предоставляет члены, которые доступны во всех проектах.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> предоставляет члены, доступные в приложениях Windows Forms.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> предоставляет члены, доступные в консольных приложениях.|Предоставляет данные, связанные только с текущим приложением или DLL.  Нет данных системного уровня, которые могут быть изменены с помощью `My.Application`.<br /><br /> Некоторые элементы доступны только для приложений Windows Forms или консольных приложений.|  
|`My.Application.Info` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>\)|Предоставляет свойства для получения сведений о приложении, например номера версии, описания, загруженных сборок и т. д.|  
|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|Предоставляет свойства и методы для записи сведений о событиях и исключениях в прослушиватели журнала приложения.|  
|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|Предоставляет свойства для управления компонентами компьютера, такими как аудио, часы, клавиатура, файловая система и т.д.|  
|`My.Computer.Audio` \(<xref:Microsoft.VisualBasic.Devices.Audio>\)|Предоставляет методы для воспроизведения звука.|  
|`My.Computer.Clipboard` \(<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>\)|Предоставляет методы для управления буфером обмена.|  
|`My.Computer.Clock` \(<xref:Microsoft.VisualBasic.Devices.Clock>\)|Предоставляет свойства, обеспечивающие доступ к текущему местному времени и универсальному времени \(эквивалент времени по Гринвичу\) из системных часов.|  
|`My.Computer.FileSystem` \(<xref:Microsoft.VisualBasic.FileIO.FileSystem>\)|Предоставляет свойства и методы для работы с дисками, файлами и каталогами.|  
|`My.Computer.FileSystem.SpecialDirectories` \(<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>\)|Предоставляет свойства для доступа к каталогам, на которые часто даются ссылки.|  
|`My.Computer.Info` \(<xref:Microsoft.VisualBasic.Devices.ComputerInfo>\)|Предоставляет свойства для получения сведений о памяти компьютера, загруженных сборках, имени и операционной системе.|  
|`My.Computer.Keyboard` \(<xref:Microsoft.VisualBasic.Devices.Keyboard>\)|Предоставляет свойства для доступа к текущему состоянию клавиатуры \(например, к сведениям о том, какие клавиши нажимает пользователь\), а также предоставляет метод для отправки сведений о нажатии клавиш в активное окно.|  
|`My.Computer.Mouse` \(<xref:Microsoft.VisualBasic.Devices.Mouse>\)|Предоставляет свойства для получения сведений о формате и конфигурации мыши, установленной на локальном компьютере.|  
|`My.Computer.Network` \(<xref:Microsoft.VisualBasic.Devices.Network>\)|Предоставляет свойство, событие и методы для взаимодействия с сетью, к которой подключен компьютер.|  
|`My.Computer.Ports` \(<xref:Microsoft.VisualBasic.Devices.Ports>\)|Предоставляет свойства и методы для доступа к последовательным портам компьютера.|  
|`My.Computer.Registry` \(<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>\)|Предоставляет свойства и методы для управления реестром.|  
|[Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)|Предоставляет свойства для доступа к экземпляру каждой формы Windows Forms, объявленной в текущем проекте.|  
|`My.Log` \(<xref:Microsoft.VisualBasic.Logging.AspLog>\)|Предоставляет свойство и методы для записи сведений о событиях и исключениях в прослушиватели журнала приложения для веб\-приложений.|  
|[Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)|Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.  Объект `My.Request` содержит сведения о текущем запросе HTTP.<br /><br /> Объект `My.Request` доступен только для приложений [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].|  
|[Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)|Предоставляет свойства и классы для доступа к ресурсам приложения.|  
|[Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)|Получает объект <xref:System.Web.HttpResponse>, связанный с <xref:System.Web.UI.Page>.  Этот объект позволяет отправить клиенту ответные данные HTTP и содержит сведения об этом ответе.<br /><br /> Объект `My.Response` доступен только для приложений [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].|  
|[Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)|Предоставляет свойства и методы для доступа к параметрам приложения.|  
|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|Предоставляет доступ к сведениям о текущем пользователе.|  
|[Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)|Предоставляет свойства для создания и доступа к одному экземпляру каждой веб\-службы XML, на которую ссылается текущий проект.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|Предоставляет методы и свойства для анализа структурированных текстовых файлов.|  
  
## См. также  
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../../visual-basic/index.md)