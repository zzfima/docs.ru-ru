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
ms.openlocfilehash: c45ab03ec4577d88953b0e43531082a46c29e8fd
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053534"
---
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="eb286-102">Устранение неполадок: невозможно установить приложение-службу</span><span class="sxs-lookup"><span data-stu-id="eb286-102">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="eb286-103">Если приложение-служба не устанавливается надлежащим образом, убедитесь, что для свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> класса службы задано значение, которое отображается в установщике этой службы.</span><span class="sxs-lookup"><span data-stu-id="eb286-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="eb286-104">Для правильной установки службы необходимо, чтобы эти значения совпадали.</span><span class="sxs-lookup"><span data-stu-id="eb286-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb286-105">Сведения о ходе установки также можно найти в журналах установки.</span><span class="sxs-lookup"><span data-stu-id="eb286-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="eb286-106">Также убедитесь, что у вас не установлена другая служба с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="eb286-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="eb286-107">Для успешной установки необходимо, чтобы у каждой службы было уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="eb286-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb286-108">См. также</span><span class="sxs-lookup"><span data-stu-id="eb286-108">See also</span></span>

- [<span data-ttu-id="eb286-109">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="eb286-109">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
