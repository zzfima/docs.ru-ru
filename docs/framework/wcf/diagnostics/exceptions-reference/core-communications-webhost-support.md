---
title: 'Основное взаимодействие: поддержка Webhost'
ms.date: 03/30/2017
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
ms.openlocfilehash: 724dc2eb66d058920fda07af899cd7464182c438
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471681"
---
# <a name="core-communications-webhost-support"></a>Основное взаимодействие: поддержка Webhost
В этом разделе перечислены все исключения, вызываемые средствами поддержки Webhost.  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|Эта служба требует совместимости с ASP.NET. Она должна также быть размещена в IIS. Либо разместите службу в IIS с включенной совместимостью с ASP.NET в файле Web.config, либо задайте для свойства AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode значение, отличное от "Required".|  
|Hosting_ListenerNotFoundForActivationInRecycling|В настоящее время ни один канал не ожидает передачу данных на заданном адресе. Если приложение перезапускается, служба закрывается.|  
|Hosting_NonHTTPInCompatibilityMode|При совместимости с ASP.NET поддерживаются только протоколы HTTP и HTTPS. Удалите указанную конечную точку или отключите совместимость с ASP.NET для приложения.|  
|Hosting_ProcessNotExecutingUnderHostedContext|Указанный процесс размещения невозможно вызвать в текущей среде размещения. Этот API требует, чтобы вызывающее приложение было размещено в службах IIS или в службе активации Windows.|  
|Hosting_ServiceCompatibilityRequire|Активировать службу невозможно, поскольку она требует совместимости с ASP.NET. Совместимость с ASP.NET для этого приложения не включена. Либо включите совместимость с ASP.NET в файле Web.config, либо установите AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
