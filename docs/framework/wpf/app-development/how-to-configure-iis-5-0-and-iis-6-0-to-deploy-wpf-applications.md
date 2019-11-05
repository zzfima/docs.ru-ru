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
ms.openlocfilehash: a731dc49556a73c585c6201a80ea3ea77c15cb11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124417"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF

Можно развернуть [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложение с большинства веб-серверов, если оно настроено с использованием соответствующих типов MIME. По умолчанию Microsoft службы IIS (IIS) 7,0 настроены с этими типами MIME, но Microsoft службы IIS (IIS) 5,0 и Microsoft службы IIS (IIS) 6,0.

В этом разделе описано, как настроить Microsoft службы IIS (IIS) 5,0 и Microsoft службы IIS (IIS) 6,0 для развертывания приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

> [!NOTE]
> Вы можете проверить строку *UserAgent* в реестре, чтобы определить, установлена ли в системе .NET Framework. Дополнительные сведения и сценарий, проверяющий строку *UserAgent* для определения того, установлена ли .NET Framework в системе, см. в разделе [обнаружение установки .NET Framework 3,0](how-to-detect-whether-the-net-framework-3-0-is-installed.md).

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a>Настройка параметра срока действия содержимого

Следует установить параметр срока действия содержимого на 1 минуту. В следующей процедуре показано, как это сделать с IIS.

1. Выберите в меню **Пуск** пункт **Администрирование** и щелкните строку **Диспетчер служб IIS**. Кроме этого, приложение можно запустить, набрав в командной строке "%SystemRoot%\system32\inetsrv\iis.msc".

2. Разверните дерево IIS, пока не найдете узел **веб-сайта по умолчанию** .

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

Следующий пример Microsoft Visual Basic Scripting Edition (VBScript) автоматически добавляет необходимые типы MIME в IIS. Чтобы использовать скрипт, скопируйте код в VBS-файл на своем сервере. Затем запустите сценарий, запустив файл из командной строки или дважды щелкнув файл в проводнике Microsoft Windows.

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
> При многократном выполнении этого сценария создается несколько записей сопоставлений MIME в метабазе Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0.

После выполнения этого скрипта могут не отображаться дополнительные типы MIME из консоли управления Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0. Однако эти типы MIME были добавлены в метабазу Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0. В следующем скрипте будут показаны все типы MIME в метабазе Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0.

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
