---
title: Объекты
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic]
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
ms.openlocfilehash: 2108e36956ada98e48e6ab05cec56dbf2a12b3dd
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838264"
---
# <a name="objects-visual-basic"></a>Объекты (Visual Basic)
В этом разделе приводятся ссылки на другие разделы, содержащие описание объектов времени выполнения Visual Basic и таблицы процедур, свойств и событий их элементов.  
  
## <a name="visual-basic-run-time-objects"></a>Объекты времени выполнения Visual Basic  
  
|||  
|---|---|  
|<xref:Microsoft.VisualBasic.Collection>|Предлагает удобный способ просматривать связанную группу элементов в виде одного объекта.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|Содержит сведения об ошибках во время выполнения.|  
|Объект `My.Application` состоит из следующих классов:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> включает элементы, доступные во всех проектах;<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> включает элементы, доступные в приложениях Windows Forms;<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> включает элементы, доступные в консольных приложениях.|Предоставляет данные, связанные только с текущим приложением или DLL. С помощью `My.Application` нельзя изменять данные системного уровня.<br /><br /> Некоторые элементы доступны только для приложений Windows Forms или консольных приложений.|  
|`My.Application.Info` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>)|Предлагает свойства для получения сведений о приложениях, например номер версии, описание, загруженные сборки и т. п.|  
|`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)|Предоставляет свойство и методы для записи сведений о событиях и исключениях в прослушиватели журнала приложения.|  
|`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)|Включает свойства для управления компонентами компьютера, такими как звук, часы, клавиатура, файловая система и т. д.|  
|`My.Computer.Audio` (<xref:Microsoft.VisualBasic.Devices.Audio>)|Предоставляет методы для воспроизведения звуков.|  
|`My.Computer.Clipboard` (<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>)|Предоставляет методы для управления буфером обмена.|  
|`My.Computer.Clock` (<xref:Microsoft.VisualBasic.Devices.Clock>)|Включает свойства для доступа к текущему местному времени и времени в формате UTC (эквиваленту времени по Гринвичу) из системных часов.|  
|`My.Computer.FileSystem` (<xref:Microsoft.VisualBasic.FileIO.FileSystem>)|Включает свойства и методы для работы с дисками, файлами и каталогами.|  
|`My.Computer.FileSystem.SpecialDirectories` (<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>)|Включает свойства для доступа к часто используемым каталогам.|  
|`My.Computer.Info` (<xref:Microsoft.VisualBasic.Devices.ComputerInfo>)|Предлагает свойства для получения сведений о памяти, загруженных сборках, имени и операционной системе компьютера.|  
|`My.Computer.Keyboard` (<xref:Microsoft.VisualBasic.Devices.Keyboard>)|Предлагает свойства для доступа к текущему состоянию клавиатуры, в частности к сведениям о нажатых в настоящий момент клавишах, а также метод для отправки сообщений о нажатиях клавиш активному окну.|  
|`My.Computer.Mouse` (<xref:Microsoft.VisualBasic.Devices.Mouse>)|Предлагает свойства для получения сведений о формате и конфигурации мыши, установленной на локальном компьютере.|  
|`My.Computer.Network` (<xref:Microsoft.VisualBasic.Devices.Network>)|Включает свойство, событие и методы для взаимодействия с сетью, к которой подключен компьютер.|  
|`My.Computer.Ports` (<xref:Microsoft.VisualBasic.Devices.Ports>)|Предлагает свойство и метод для доступа к последовательным портам компьютера.|  
|`My.Computer.Registry` (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)|Включает свойства и методы для управления реестром.|  
|[Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)|Предлагает свойства для доступа к экземпляру каждой формы Windows Forms, объявленной в текущем проекте.|  
|`My.Log` (<xref:Microsoft.VisualBasic.Logging.AspLog>)|Включает свойство и методы для записи сведений о событиях и исключениях в прослушивателе журнала для веб-приложений.|  
|[Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)|Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы. Объект `My.Request` содержит сведения о текущем HTTP-запросе.<br /><br /> Объект `My.Request` доступен только для приложений ASP.NET.|  
|[Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)|Содержит свойства и классы для доступа к ресурсам приложения.|  
|[Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)|Возвращает объект <xref:System.Web.HttpResponse>, связанный с <xref:System.Web.UI.Page>. Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.<br /><br /> Объект `My.Response` доступен только для приложений ASP.NET.|  
|[Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)|Включает свойства и методы для доступа к параметрам приложения.|  
|`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)|Предоставляет доступ к сведениям о текущем пользователе.|  
|[Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)|Предлагает свойства для создания экземпляров каждой веб-службы, на которую ссылается текущий проект, а также для доступа к этим экземплярам.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|Предоставляет методы и свойства для анализа структурированных текстовых файлов.|  
  
## <a name="see-also"></a>См. также:

- [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)
