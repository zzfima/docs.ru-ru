---
title: Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF
titleSuffix: ''
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
ms.openlocfilehash: d557ac6cd380edcbc93b5315f6356697817274bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740409"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="8d7d8-102">Практическое руководство. Настройка служб IIS 5.0 и IIS 6.0 для развертывания приложений WPF</span><span class="sxs-lookup"><span data-stu-id="8d7d8-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="8d7d8-103">Можно развернуть [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложение с большинства веб-серверов, если оно настроено с использованием соответствующих типов MIME.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate Multipurpose Internet Mail Extensions (MIME) types.</span></span> <span data-ttu-id="8d7d8-104">По умолчанию Microsoft службы IIS (IIS) 7,0 настроены с этими типами MIME, но Microsoft службы IIS (IIS) 5,0 и Microsoft службы IIS (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-104">By default, Microsoft Internet Information Services (IIS) 7.0 is configured with these MIME types, but Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 are not.</span></span>

<span data-ttu-id="8d7d8-105">В этом разделе описано, как настроить Microsoft службы IIS (IIS) 5,0 и Microsoft службы IIS (IIS) 6,0 для развертывания приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d7d8-105">This topic describes how to configure Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="8d7d8-106">Вы можете проверить строку *UserAgent* в реестре, чтобы определить, установлена ли в системе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="8d7d8-107">Дополнительные сведения и сценарий, проверяющий строку *UserAgent* для определения того, установлена ли .NET Framework в системе, см. в разделе [обнаружение установки .NET Framework 3,0](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="8d7d8-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="8d7d8-108">Настройка параметра срока действия содержимого</span><span class="sxs-lookup"><span data-stu-id="8d7d8-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="8d7d8-109">Следует установить параметр срока действия содержимого на 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="8d7d8-110">В следующей процедуре показано, как это сделать с IIS.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-110">The following procedure outlines how to do this with IIS.</span></span>

1. <span data-ttu-id="8d7d8-111">Выберите в меню **Пуск** пункт **Администрирование** и щелкните строку **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="8d7d8-112">Кроме этого, приложение можно запустить, набрав в командной строке "%SystemRoot%\system32\inetsrv\iis.msc".</span><span class="sxs-lookup"><span data-stu-id="8d7d8-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="8d7d8-113">Разверните дерево IIS, пока не найдете узел **веб-сайта по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="8d7d8-113">Expand the IIS tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="8d7d8-114">Щелкните правой кнопкой мыши **Веб-сайт по умолчанию** и выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="8d7d8-115">Перейдите на вкладку **Заголовки HTTP** и нажмите кнопку "Активировать срок действия содержимого".</span><span class="sxs-lookup"><span data-stu-id="8d7d8-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="8d7d8-116">Установите срок действия контента равным одной минуте.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="8d7d8-117">Регистрация типов MIME и расширений файлов</span><span class="sxs-lookup"><span data-stu-id="8d7d8-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="8d7d8-118">Необходимо зарегистрировать несколько типов MIME и расширений файлов, чтобы браузер в клиентской системе мог загрузить правильный обработчик.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-118">You must register several MIME types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="8d7d8-119">Необходимо добавить следующие типы.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-119">You need to add the following types:</span></span>

|<span data-ttu-id="8d7d8-120">Расширение</span><span class="sxs-lookup"><span data-stu-id="8d7d8-120">Extension</span></span>|<span data-ttu-id="8d7d8-121">Тип MIME</span><span class="sxs-lookup"><span data-stu-id="8d7d8-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="8d7d8-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="8d7d8-122">.manifest</span></span>|<span data-ttu-id="8d7d8-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="8d7d8-123">application/manifest</span></span>|
|<span data-ttu-id="8d7d8-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="8d7d8-124">.xaml</span></span>|<span data-ttu-id="8d7d8-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="8d7d8-125">application/xaml+xml</span></span>|
|<span data-ttu-id="8d7d8-126">.application</span><span class="sxs-lookup"><span data-stu-id="8d7d8-126">.application</span></span>|<span data-ttu-id="8d7d8-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="8d7d8-127">application/x-ms-application</span></span>|
|<span data-ttu-id="8d7d8-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="8d7d8-128">.xbap</span></span>|<span data-ttu-id="8d7d8-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="8d7d8-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="8d7d8-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="8d7d8-130">.deploy</span></span>|<span data-ttu-id="8d7d8-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="8d7d8-131">application/octet-stream</span></span>|
|<span data-ttu-id="8d7d8-132">.xps</span><span class="sxs-lookup"><span data-stu-id="8d7d8-132">.xps</span></span>|<span data-ttu-id="8d7d8-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="8d7d8-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="8d7d8-134">Не нужно регистрировать типы MIME или расширения файлов в клиентских системах.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-134">You do not need to register MIME types or file extensions on client systems.</span></span> <span data-ttu-id="8d7d8-135">Они регистрируются автоматически при установке Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="8d7d8-136">Следующий пример Microsoft Visual Basic Scripting Edition (VBScript) автоматически добавляет необходимые типы MIME в IIS.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary MIME types to IIS.</span></span> <span data-ttu-id="8d7d8-137">Чтобы использовать скрипт, скопируйте код в VBS-файл на своем сервере.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="8d7d8-138">Затем запустите сценарий, запустив файл из командной строки или дважды щелкнув файл в проводнике Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-138">Then, run the script by running the file from the command line or double-clicking the file in Microsoft Windows Explorer.</span></span>

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
> <span data-ttu-id="8d7d8-139">При многократном выполнении этого сценария создается несколько записей сопоставлений MIME в метабазе Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-139">Running this script multiple times creates multiple MIME map entries in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

<span data-ttu-id="8d7d8-140">После выполнения этого скрипта могут не отображаться дополнительные типы MIME из консоли управления Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-140">After you have run this script, you may not see additional MIME types from the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 Microsoft Management Console (MMC).</span></span> <span data-ttu-id="8d7d8-141">Однако эти типы MIME были добавлены в метабазу Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-141">However, these MIME types have been added to the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span> <span data-ttu-id="8d7d8-142">В следующем скрипте будут показаны все типы MIME в метабазе Microsoft службы IIS (IIS) 5,0 или Microsoft службы IIS (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="8d7d8-142">The following script will display all the MIME types in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

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

<span data-ttu-id="8d7d8-143">Сохраните скрипт в виде файла `.vbs` (например, `DiscoverIISMimeTypes.vbs`) и запустите его из командной строки с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="8d7d8-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
