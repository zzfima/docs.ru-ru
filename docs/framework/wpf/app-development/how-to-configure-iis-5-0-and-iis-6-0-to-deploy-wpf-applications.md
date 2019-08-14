---
title: Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: a1e58aef6d02b6cf05a126b6afd25ab2a6004002
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972298"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Приложение можно развернуть с большинства веб-серверов, если они настроены с использованием соответствующих типов MIME. По умолчанию [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] настраивается с этими типами MIME [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] , а [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] не с помощью.

В этом разделе описывается настройка [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] и [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] для развертывания приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

> [!NOTE]
> Вы можете проверить строку *UserAgent* в реестре, чтобы определить, установлена ли в системе .NET Framework. Дополнительные сведения и сценарий, проверяющий строку *UserAgent* для определения того, установлена ли .NET Framework в системе, см. в разделе [обнаружение установки .NET Framework 3,0](how-to-detect-whether-the-net-framework-3-0-is-installed.md).

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a>Настройка параметра срока действия содержимого

Следует установить параметр срока действия содержимого на 1 минуту. В следующей процедуре показано, как это сделать с помощью [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].

1. Выберите в меню **Пуск** пункт **Администрирование** и щелкните строку **Диспетчер служб IIS**. Кроме этого, приложение можно запустить, набрав в командной строке "%SystemRoot%\system32\inetsrv\iis.msc".

2. Разворачивайте дерево [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)], пока не найдете узел **Веб-сайт по умолчанию**.

3. Щелкните правой кнопкой мыши **Веб-сайт по умолчанию** и выберите в контекстном меню пункт **Свойства**.

4. Перейдите на вкладку **Заголовки HTTP** и нажмите кнопку "Активировать срок действия содержимого".

5. Установите срок действия контента равным одной минуте.

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a>Регистрация типов MIME и расширений файлов

Необходимо зарегистрировать несколько типов MIME и расширений файлов, чтобы браузер в клиентской системе мог загрузить правильный обработчик. Необходимо добавить следующие типы.

|Расширение|Тип MIME|
|---------------|---------------|
|.manifest|application/manifest|
|.xaml|application/xaml+xml|
|.application|application/x-ms-application|
|.xbap|application/x-ms-xbap|
|.deploy|application/octet-stream|
|.xps|application/vnd.ms-xpsdocument|

> [!NOTE]
> Не нужно регистрировать типы MIME или расширения файлов в клиентских системах. Они регистрируются автоматически при установке Microsoft .NET Framework.

Следующий пример Microsoft Visual Basic Scripting Edition (VBScript) автоматически добавляет необходимые типы MIME в [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]. Чтобы использовать скрипт, скопируйте код в VBS-файл на своем сервере. Затем выполните скрипт, запустив файл из командной строки или дважды щелкнув этот файл в [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].

```vb
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

' Get the MimeMap object
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
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> Многократное выполнение этого сценария создает несколько записей сопоставлений MIME [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] в [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] метабазе или.

После выполнения этого скрипта могут не отображаться дополнительные типы MIME из [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)] Однако эти типы MIME были добавлены в [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] метабазу или. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] В следующем скрипте будут показаны все типы MIME в [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] метабазе или. [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

Сохраните скрипт в виде файла `.vbs` (например, `DiscoverIISMimeTypes.vbs`) и запустите его из командной строки с помощью следующей команды:

```console
cscript DiscoverIISMimeTypes.vbs
```
