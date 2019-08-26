---
title: 'Устранение неполадок: невозможно установить приложение-службу'
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
ms.openlocfilehash: d04a0ddcef9ff7c31abd422f7f9fba34e804d2b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935415"
---
# <a name="troubleshooting-service-application-wont-install"></a>Устранение неполадок: невозможно установить приложение-службу
Если приложение-служба не устанавливается надлежащим образом, убедитесь, что для свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> класса службы задано значение, которое отображается в установщике этой службы. Для правильной установки службы необходимо, чтобы эти значения совпадали.  
  
> [!NOTE]
> Сведения о ходе установки также можно найти в журналах установки.  
  
 Также убедитесь, что у вас не установлена другая служба с таким же именем. Для успешной установки необходимо, чтобы у каждой службы было уникальное имя.  
  
## <a name="see-also"></a>См. также

- [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
