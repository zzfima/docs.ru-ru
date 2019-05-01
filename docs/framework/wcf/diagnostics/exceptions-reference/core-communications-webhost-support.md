---
title: 'Основное взаимодействие: Поддержка WebHost'
ms.date: 03/30/2017
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
ms.openlocfilehash: 8ee107ffcb9fab629541ce004d1c587fcad652c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998716"
---
# <a name="core-communications-webhost-support"></a>Основное взаимодействие: Поддержка WebHost

В этом разделе перечислены все исключения, вызываемые средствами поддержки Webhost.

## <a name="exception-list"></a>Список исключений

|Код ресурса|Строка ресурса|
|-------------------|---------------------|
|Hosting_CompatibilityServiceNotHosted|Эта служба требует совместимости с ASP.NET. Она должна также быть размещена в IIS. Либо разместите службу в IIS с включенной совместимостью с ASP.NET в файле Web.config, либо задайте для свойства AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode значение, отличное от "Required".|
|Hosting_ListenerNotFoundForActivationInRecycling|В настоящее время ни один канал не ожидает передачу данных на заданном адресе. Если приложение перезапускается, служба закрывается.|
|Hosting_NonHTTPInCompatibilityMode|При совместимости с ASP.NET поддерживаются только протоколы HTTP и HTTPS. Удалите указанную конечную точку или отключите совместимость с ASP.NET для приложения.|
|Hosting_ProcessNotExecutingUnderHostedContext|Указанный процесс размещения невозможно вызвать в текущей среде размещения. Этот API требует, чтобы вызывающее приложение было размещено в службах IIS или в службе активации Windows.|
|Hosting_ServiceCompatibilityRequire|Активировать службу невозможно, поскольку она требует совместимости с ASP.NET. Совместимость с ASP.NET для этого приложения не включена. Либо включите совместимость с ASP.NET в файле Web.config, либо установите AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
