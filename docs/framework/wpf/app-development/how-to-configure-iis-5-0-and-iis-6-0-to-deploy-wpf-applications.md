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
ms.openlocfilehash: 6fa00c4ced8c05d056703560e5740689c6dcfe39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61981459"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="9f657-102">Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF</span><span class="sxs-lookup"><span data-stu-id="9f657-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="9f657-103">Приложение [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разворачивать с большинства веб-серверов при условии, что они настроены с соответствующими типами [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] types.</span></span> <span data-ttu-id="9f657-104">По умолчанию [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] настроена с типами [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)], в отличие от [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] и [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-104">By default, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] is configured with these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types, but [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] are not.</span></span>

<span data-ttu-id="9f657-105">В этом разделе описывается настройка [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] и [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] для развертывания приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-105">This topic describes how to configure [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="9f657-106">Вы можете проверить *UserAgent* строку в реестре, чтобы определить, имеет ли система установлена платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f657-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="9f657-107">Дополнительные сведения и скрипт, проверяющий *UserAgent* строку, чтобы определить, установлена ли платформа .NET Framework в системе, см. в разделе [обнаруживать ли .NET Framework 3.0 устанавливается](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="9f657-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="9f657-108">Настройка параметра срока действия содержимого</span><span class="sxs-lookup"><span data-stu-id="9f657-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="9f657-109">Следует установить параметр срока действия содержимого на 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="9f657-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="9f657-110">В следующей процедуре показано, как это сделать с помощью [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-110">The following procedure outlines how to do this with [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span>

1. <span data-ttu-id="9f657-111">Выберите в меню **Пуск** пункт **Администрирование** и щелкните строку **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="9f657-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="9f657-112">Кроме этого, приложение можно запустить, набрав в командной строке "%SystemRoot%\system32\inetsrv\iis.msc".</span><span class="sxs-lookup"><span data-stu-id="9f657-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="9f657-113">Разворачивайте дерево [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)], пока не найдете узел **Веб-сайт по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="9f657-113">Expand the [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="9f657-114">Щелкните правой кнопкой мыши **Веб-сайт по умолчанию** и выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9f657-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="9f657-115">Перейдите на вкладку **Заголовки HTTP** и нажмите кнопку "Активировать срок действия содержимого".</span><span class="sxs-lookup"><span data-stu-id="9f657-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="9f657-116">Установите срок действия контента равным одной минуте.</span><span class="sxs-lookup"><span data-stu-id="9f657-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="9f657-117">Регистрация типов MIME и расширений файлов</span><span class="sxs-lookup"><span data-stu-id="9f657-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="9f657-118">Вы должны зарегистрировать несколько типов [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] и расширений файлов, чтобы браузер в клиентской системе мог загрузить правильный обработчик.</span><span class="sxs-lookup"><span data-stu-id="9f657-118">You must register several [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="9f657-119">Необходимо добавить следующие типы.</span><span class="sxs-lookup"><span data-stu-id="9f657-119">You need to add the following types:</span></span>

|<span data-ttu-id="9f657-120">Расширение</span><span class="sxs-lookup"><span data-stu-id="9f657-120">Extension</span></span>|<span data-ttu-id="9f657-121">Тип MIME</span><span class="sxs-lookup"><span data-stu-id="9f657-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="9f657-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="9f657-122">.manifest</span></span>|<span data-ttu-id="9f657-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="9f657-123">application/manifest</span></span>|
|<span data-ttu-id="9f657-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="9f657-124">.xaml</span></span>|<span data-ttu-id="9f657-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="9f657-125">application/xaml+xml</span></span>|
|<span data-ttu-id="9f657-126">.application</span><span class="sxs-lookup"><span data-stu-id="9f657-126">.application</span></span>|<span data-ttu-id="9f657-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="9f657-127">application/x-ms-application</span></span>|
|<span data-ttu-id="9f657-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="9f657-128">.xbap</span></span>|<span data-ttu-id="9f657-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="9f657-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="9f657-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="9f657-130">.deploy</span></span>|<span data-ttu-id="9f657-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="9f657-131">application/octet-stream</span></span>|
|<span data-ttu-id="9f657-132">.xps</span><span class="sxs-lookup"><span data-stu-id="9f657-132">.xps</span></span>|<span data-ttu-id="9f657-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="9f657-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="9f657-134">В клиентских системах регистрация типов [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] или расширений файлов не требуется.</span><span class="sxs-lookup"><span data-stu-id="9f657-134">You do not need to register [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types or file extensions on client systems.</span></span> <span data-ttu-id="9f657-135">Они регистрируются автоматически при установке Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f657-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="9f657-136">В следующем примере Microsoft Visual Basic Scripting Edition (VBScript) автоматически добавляет необходимые [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] типов [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types to [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span> <span data-ttu-id="9f657-137">Чтобы использовать скрипт, скопируйте код в VBS-файл на своем сервере.</span><span class="sxs-lookup"><span data-stu-id="9f657-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="9f657-138">Затем выполните скрипт, запустив файл из командной строки или дважды щелкнув этот файл в [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>

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
> <span data-ttu-id="9f657-139">При многократном запуске скрипта создастся множество записей сопоставления [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] в метабазе [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-139">Running this script multiple times creates multiple [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] map entries in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>

<span data-ttu-id="9f657-140">После выполнения этого скрипта дополнительные типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] могут быть не видны из служб [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-140">After you have run this script, you may not see additional [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types from the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span></span> <span data-ttu-id="9f657-141">Однако эти типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] были добавлены в метабазу [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-141">However, these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types have been added to the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span> <span data-ttu-id="9f657-142">Следующий скрипт отобразит все типы [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] в метабазе [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] или [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f657-142">The following script will display all the [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>

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

<span data-ttu-id="9f657-143">Сохраните скрипт в виде файла `.vbs` (например, `DiscoverIISMimeTypes.vbs`) и запустите его из командной строки с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9f657-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
