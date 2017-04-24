---
title: "Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "настройка параметра срока действия содержимого"
  - "приложения, развертывание"
  - "Настройка веб-серверов для развертывания приложений WPF"
  - "параметр срока действия содержимого, подстройка"
  - "развертывание приложений"
  - "расширения файлов, регистрация"
  - "типы MIME, регистрация"
  - "регистрация расширений файлов"
  - "регистрация типов MIME"
  - "веб-серверы, настройка для развертывания приложений WPF"
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF
Можно развертывать приложение [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] с большинства веб\-серверов, если они настроены с соответствующими типами[!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)].  По умолчанию конфигурация службы [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] содержит типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] в отличие от служб [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] и [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].  
  
 В этом разделе описывается настройка служб [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] и [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]для развертывания приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
> [!NOTE]
>  Можно проверить строку *UserAgent* в реестре, чтобы определить, установлен ли [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] в системе.  Сведения и скрипт, проверяющий по записи *UserAgent* наличие в системе установленного [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], см. в разделе[Проверка наличия установленной платформы .NET Framework 3.0](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).  
  
<a name="content_expiration"></a>   
## Настройка параметра срока действия содержимого  
 Следует установить параметр срока действия содержимого на 1 минуту.  В следующей процедуре показано, как это сделать с помощью службы [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].  
  
1.  Выберите в меню **Пуск** пункт **Администрирование** и щелкните строку **Диспетчер служб IIS**.  Кроме этого, приложение можно запустить, набрав в командной строке "%SystemRoot%\\system32\\inetsrv\\iis.msc".  
  
2.  Разворачивайте дерево [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)], пока не найдете узел **Используемый по умолчанию веб\-узел**.  
  
3.  Щелкните правой кнопкой мыши **используемый по умолчанию веб\-узел** и выберите пункт **Свойства** из контекстного меню.  
  
4.  Откройте вкладку **Заголовки HTTP** и нажмите кнопку "Активировать срок действия содержимого".  
  
5.  Установите срок действия содержимого, равным одной минуте.  
  
<a name="register_mime_types"></a>   
## Регистрация типов MIME и расширения файлов  
 Несколько типов [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] и расширения файлов необходимо зарегистрировать таким образом, чтобы браузер на клиентской системе мог загрузить правильный обработчик.  Нужно добавить следующие типы:  
  
|Расширение|Тип MIME|  
|----------------|--------------|  
|MANIFEST|application\/manifest|  
|.xaml|application\/xaml\+xml|  
|APPLICATION|application\/x\-ms|  
|XBAP|application\/x\-ms\-xbap|  
|DEPLOY|application\/octet\-stream|  
|XPS|application\/vnd.ms\-xpsdocument|  
  
> [!NOTE]
>  Регистрировать типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] или расширения файлов в клиентских системах необязательно.  Они регистрируются автоматически при установке [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)].  
  
 Следующий образец [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] автоматически добавляет необходимые типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] в службу [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].  Чтобы использовать скрипт, скопируйте код в VBS\-файл на сервере.  Затем выполните скрипт, запустив файл из командной строки или дважды щелкнув файл в [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].  
  
```  
' This script adds the necessary Windows Presentation Foundation MIME types   
' to an IIS Server.  
' To use this script, just double-click or execute it from a command line.  
' Running this script multiple times results in multiple entries in the IIS MimeMap.  
  
Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec  
Const ADS_PROPERTY_UPDATE = 2   
  
' Set the MIME types to be added  
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _  
    "application/xaml+xml", ".application", "application/x-ms-application", _  
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _  
    ".xps", "application/vnd.ms-xpsdocument")   
  
' Get the mimemap object   
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")  
  
' Call AddMimeType for every pair of extension/MIME type  
For counter = 0 to UBound(MimeTypesToAddArray) Step 2  
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)  
Next  
  
' Create a Shell object  
Set WshShell = CreateObject("WScript.Shell")  
  
' Stop and Start the IIS Service  
Set oExec = WshShell.Exec("net stop w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = WshShell.Exec("net start w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = Nothing  
  
' Report status to user  
WScript.Echo "Windows Presentation Foundation MIME types have been registered."  
  
' AddMimeType Sub  
Sub AddMimeType (Ext, MType)  
  
    ' Get the mappings from the MimeMap property.   
    MimeMapArray = MimeMapObj.GetEx("MimeMap")   
  
    ' Add a new mapping.   
    i = UBound(MimeMapArray) + 1   
    Redim Preserve MimeMapArray(i)   
    Set MimeMapArray(i) = CreateObject("MimeMap")   
    MimeMapArray(i).Extension = Ext   
    MimeMapArray(i).MimeType = MType   
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray  
    MimeMapObj.SetInfo  
  
End Sub  
```  
  
> [!NOTE]
>  При многократном запуске скрипта создастся множество [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] записей сопоставления в метабазе [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].  
  
 После выполнения этого скрипта дополнительные типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] могут быть не видны из служб [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].  Однако эти типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] были добавлены в метабазу служб [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].  Следующий скрипт отобразит все типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] метабазы [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].  
  
```  
' This script lists the MIME types for an IIS Server.  
' To use this script, just double-click or execute it from a command line   
' by calling cscript.exe  
  
dim mimeMapEntry, allMimeMaps  
  
' Get the mimemap object.  
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")  
allMimeMaps = mimeMapEntry.GetEx("MimeMap")  
  
' Display the mappings in the table.  
For Each mimeMap In allMimeMaps  
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")  
Next  
```  
  
 Сохраните скрипт в виде файла с расширением `.vbs` \(например, `DiscoverIISMimeTypes.vbs`\) и запустите его из командной строки с помощью следующей команды:  
  
 `cscript DiscoverIISMimeTypes.vbs`