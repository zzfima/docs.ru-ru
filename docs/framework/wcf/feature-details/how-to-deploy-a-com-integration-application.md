---
title: Практическое руководство. Развертывание приложения интеграции COM+
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: 281fe0fb93fffb84f85f19b42e8d90e86dc300c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146735"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="50bd1-102">Практическое руководство. Развертывание приложения интеграции COM+</span><span class="sxs-lookup"><span data-stu-id="50bd1-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="50bd1-103">Написанное приложение интеграции COM+ может понадобиться развернуть на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="50bd1-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="50bd1-104">В этом разделе описывается перенос приложения COM+ с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="50bd1-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="50bd1-105">Перенос размещенного в COM+ приложения интеграции</span><span class="sxs-lookup"><span data-stu-id="50bd1-105">Moving a COM+ hosted Integration App</span></span>  
  
1.  <span data-ttu-id="50bd1-106">Убедитесь, что на обоих компьютерах установлен продукт WCF.</span><span class="sxs-lookup"><span data-stu-id="50bd1-106">Ensure that WCF is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="50bd1-107">Экспортируйте приложение с компьютера A.</span><span class="sxs-lookup"><span data-stu-id="50bd1-107">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="50bd1-108">Импортируйте приложение на компьютер B.</span><span class="sxs-lookup"><span data-stu-id="50bd1-108">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="50bd1-109">Задайте корневую папку приложения.</span><span class="sxs-lookup"><span data-stu-id="50bd1-109">Set the Application Root Directory.</span></span> <span data-ttu-id="50bd1-110">По традиции это %PROGRAMFILES%/ComPlus Applications/{GUID_приложения}.</span><span class="sxs-lookup"><span data-stu-id="50bd1-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5.  <span data-ttu-id="50bd1-111">Скопируйте файлы Application.config и Application.manifest из корневой папки приложения на компьютере A в корневую папку приложения на компьютере B.</span><span class="sxs-lookup"><span data-stu-id="50bd1-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6.  <span data-ttu-id="50bd1-112">Отредактируйте адреса конечных точек службы в файле Application.config на компьютере B так, чтобы они указывали на соответствующий компьютер.</span><span class="sxs-lookup"><span data-stu-id="50bd1-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="50bd1-113">Например, измените `http://machineA/MyService` на `http://machineB/MyService`.</span><span class="sxs-lookup"><span data-stu-id="50bd1-113">For example, change `http://machineA/MyService` to `http://machineB/MyService`.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="50bd1-114">Перенос размещенного на веб-сервере приложения интеграции</span><span class="sxs-lookup"><span data-stu-id="50bd1-114">Moving a Web-hosted integration application</span></span>  
  
1.  <span data-ttu-id="50bd1-115">Убедитесь, что на обоих компьютерах установлен продукт WCF.</span><span class="sxs-lookup"><span data-stu-id="50bd1-115">Ensure that WCF is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="50bd1-116">Экспортируйте приложение с компьютера A.</span><span class="sxs-lookup"><span data-stu-id="50bd1-116">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="50bd1-117">Импортируйте приложение на компьютер B.</span><span class="sxs-lookup"><span data-stu-id="50bd1-117">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="50bd1-118">Создайте виртуальный корневой каталог IIS на компьютере B.</span><span class="sxs-lookup"><span data-stu-id="50bd1-118">Create an IIS vroot on machine B.</span></span>  
  
5.  <span data-ttu-id="50bd1-119">Скопируйте файл .SVC (имя_компонента.svc) и файл Web.config из виртуального корневого каталога на компьютере A в только что созданный виртуальный корневой каталог на компьютере B.</span><span class="sxs-lookup"><span data-stu-id="50bd1-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bd1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="50bd1-120">See also</span></span>

- [<span data-ttu-id="50bd1-121">Общие сведения об интеграции с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="50bd1-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
- [<span data-ttu-id="50bd1-122">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="50bd1-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
- [<span data-ttu-id="50bd1-123">Практическое руководство. Использование программы командной строки настройки модели служб COM+</span><span class="sxs-lookup"><span data-stu-id="50bd1-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
