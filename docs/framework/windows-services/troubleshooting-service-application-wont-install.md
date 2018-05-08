---
title: Устранение неполадок Службы приложения реализовано&#39;t Install
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-service-application-won39t-install"></a>Устранение неполадок Службы приложения реализовано&#39;t Install
Если приложение службы не устанавливается правильно, проверьте, убедитесь, что <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства для класса службы имеет значение то же значение, как показано в программе установки для этой службы. Значение должно быть одинаковым в обоих случаях для правильной установки службы.  
  
> [!NOTE]
>  Можно также найти журналы установки, чтобы получить отзывы о ходе процесса установки.  
  
 Необходимо также проверить, чтобы убедиться, что другая служба с таким именем уже установлен. Имена служб должны быть уникальными для успешной установки.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
