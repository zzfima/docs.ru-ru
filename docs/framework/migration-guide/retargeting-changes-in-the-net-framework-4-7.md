---
title: "Изменения целевой платформы в .NET Framework 4.7 | Документация Майкрософт"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes,.NET Framework
- retargeting changes,.NET Framework 4.7
- application compatibility
ms.assetid: d98bf1e3-0017-4933-8e7b-191ac3542fcc
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: fccd83571b47e3c2a6f995893c6260ae91eae517
ms.openlocfilehash: 53c3bc41e319fe122605993d4013e6f04832c89c
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-47"></a>Изменения целевой платформы в .NET Framework 4.7

В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в .NET Framework 4.7. Они не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но влияют в случае установленной версии 4.7. Платформа .NET Framework 4.7 включает изменения целевой платформы в следующих областях:  

-   [Ядро](#Core)  
-   [ASP.NET](#asp) 
-   [Windows Communication Foundation (WCF)](#WCF)  
-   [Windows Presentation Foundation (WPF)](#WPF)
 
 Столбец "Scope" в следующих таблицах определяет важность каждого изменения.  
  
-   Основное. Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода. Обратите внимание, что ни одно из изменений целевой платформы не попадает в эту категорию.  
  
-   Незначительное. Изменение влияет на небольшое количество приложений или требует незначительного изменения кода.  
  
-   Пограничное. Изменение влияет на приложения в исключительных ситуациях.  
  
-   Прозрачное. Изменение не оказывает особого влияния на разработчика или пользователя приложения. При этом вносить изменения в приложения не требуется.  
  
## <a name="a-namecore--core"></a><a name="Core" /> Ядро

| Функция | Изменение | Последствия | Область |
|----|----|----|----|
|<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> | Приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, ожидают присвоения этому свойству значения указателя <xref:System.IntPtr> на указанное расположение в памяти, где содержится значение HWND.<br/></br>Начиная с приложений, предназначенных для .NET Framework 4.7, приложение Windows Forms может установить значение этого свойства с помощью следующего кода: <br/><br/>` cspParameters.ParentWindowHandle = form.Handle; ` | В приложениях, где такое изменение поведения является неудобным, можно отказаться от нового поведения. Аналогично, в приложениях, ориентированных на более ранние версии .NET Framework, но работающих на платформе .NET Framework 4.7, можно выбрать новое поведение. Дополнительные сведения см. в статье [Mitigation: CspParameters.ParentWindowHandle Expects an HWND](../../../docs/framework/migration-guide/mitigation-cspparameters-parentwindowhandle-expects-an-hwnd.md) (Устранение рисков. CspParameters.ParentWindowHandle ожидает HWND). | Дополнительный номер |
| Сериализация с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> | Начиная с приложений, ориентированных на .NET Framework 4.7, сериализация управляющих символов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> теперь совместима с ECMAScript V6 и V8 | Это изменение соответствует стандарту ECMAScript и не должно оказывать значительного влияния. В противном случае доступен переключатель совместимости, позволяющий восстановить прежнее поведение. Дополнительные сведения см. в статье [Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer](../../../docs/framework/migration-guide/mitigation-serialization-control-characters.md)  | Пограничный случай |

## <a name="a-nameasp--aspnet"></a><a name="asp" /> ASP.NET

| Функция  |Изменение  |Последствия | Область | 
---------|---------|---------|-----|
Регулирование одновременных запросов за сеанс | В платформе .NET Framework 4.6.2 и более ранних версиях ASP.NET выполняет запросы с тем же <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> последовательно, а ASP.NET всегда выдает <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> через файл cookie по умолчанию. Если страница загружается долго, нажатие клавиши <kbd> F5 </kbd> в браузере значительно снижает производительность сервера.<br/><br/>Начиная с .NET Framework 4.7, счетчик отслеживает запросы в очереди и завершает запросы, если они превышают заданное ограничение. Значение по умолчанию — 50. Если ограничение достигнуто, в журнал событий записывается предупреждение, а в журнале IIS может быть записан ответ HTTP 500.|Это изменение повышает общую производительность сервера.<br/><br/>Чтобы восстановить прежнее поведение, можно добавить следующий параметр в файл web.config для отказа от нового поведения.<br/><br/>`<appSettings>`<br/>&nbsp;&nbsp;&nbsp;`<add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>`<br/>`</appSettings>` | Пограничный случай |

## <a name="a-namewcf--windows-communication-foundation"></a><a name="WCF" /> Windows Communication Foundation

| Функция  |Изменение  |Последствия | Область | 
---------|---------|---------|-----|
| Безопасность сообщений WCF | Приложения, работающие в .NET Framework 4.7 или более поздней версии, могут использовать TLS 1.1 и TLS 1.2 в защите сообщений WCF через настройки конфигурации приложения. Эту функцию следует включать отдельно; по умолчанию поддержка TLS 1.1 и TLS 1.2 в защите сообщений WCF отключена. | Поведение безопасности сообщений WCF по умолчанию остается неизменным. <br/><br/> Чтобы включить поддержку TLS 1.1 и TLS 1.2, добавьте следующий параметр конфигурации в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла `app.config` или `web.config`:  <br/><br/>`<runtime>` <br/> &nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;`<br/>&nbsp;&nbsp;&nbsp;`Switch.System.Net.DontEnableSchUseStrongCrypto=false" />`<br/>`</runtime>` | Пограничный случай |         

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> Windows Presentation Foundation (WPF)  

| Функция | Изменение | Последствия | Область |
|---|---|---|---|
| Выделение пространства элемента управления <xref:System.Windows.Controls.Grid> для столбцов со звездочкой | Начиная с приложений, предназначенных для .NET Framework 4.7, WPF заменяет алгоритм, который использовался в элементе управления <xref:System.Windows.Controls.Grid> для выделения пространства для столбцов со звездочкой (\*). | Для приложений, предназначенных для версий платформы .NET Framework, начиная с .NET Framework 4.7, это изменение влияет на фактическую ширину, назначаемую столбцам со звездочкой (\*) в ряде случаев. Если это изменение нежелательно, можно продолжить применять предыдущий алгоритм, добавив запись в файл конфигурации приложения. Дополнительные сведения см. в статье [Mitigation: Grid Control's Space Allocation to Star-columns](../../../docs/framework/migration-guide/mitigation-grid-control.md) (Устранение рисков. Выделение пространства элемента управления "сетка" для столбцов со звездочкой). | Дополнительный номер |
<xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> | В приложениях, предназначенных для .NET Framework 4.6.2 и более ранних версий, ошибка в коде обработки исключений метода <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> вызывала исключение <xref:System.NullReferenceException> вместо ожидаемого исключения (например, <xref:System.IO.DirectoryNotFoundException> или <xref:System.IO.FileNotFoundException>).<br/><br/>Начиная с приложений, ориентированных на .NET Framework 4.7, вызывается правильное исключение.  | Для приложений, предназначенных для .NET Framework 4.7 и зависящих от обработки <xref:System.NullReferenceException>, можно восстановить прежнее поведение, добавив следующий параметр конфигурации в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла `app.config`: <br/><br/>`<runtime>`<br/>&nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true"/>`<br/>`</runtime>`| Пограничный случай | 
| Включение поддержки для стека сенсорного управления или пера на основе `WM_POINTER` | Начиная с приложений, предназначенных для .NET Framework 4.7, WPF добавляет поддержку необязательного сенсорного управления на основе `WM_POINTER.  | Эта функция, которую следует включать отдельно, доступна в системах Windows, начиная с Windows 10 Creators Update. На приложения WPF, которые не включают явно поддержку сенсорного ввода или пера на основе указателя, это не влияет. Дополнительные сведения см. в статье [Устранение рисков. Поддержка сенсорного управления и пера на основе указателя](../Topic/Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md). | Пограничный случай |
| Класс <xref:System.Printing.PrintQueue> | Начиная с .NET Framework 4.7, API-интерфейсы печати WPF, использующие по умолчанию класс <xref:System.Printing.PrintQueue>, вызывают API-интерфейс пакета документов печати Windows вместо уже устаревшего API-интерфейса печати XPS.<br/><br/>Старый стек печати продолжает работать в предыдущих версиях Windows, как и раньше. | Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API. <br/><br/>Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение `UseXpsOMPrinting` `REG_DWORD` в разделе реестра `HKEY_CURRENT_USER\Software\Microsoft.NETFramework\Windows Presentation Foundation\Printing` равным 1. | Пограничный случай | 
## <a name="see-also"></a>См. также
[Совместимость приложений в .NET Framework 4.7](Application%20Compatibility%20in%20the%20.NET%20Framework%204.7.md)

