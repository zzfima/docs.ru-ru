---
title: Практическое руководство. Включение службы совместного использования портов Net.TCP
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 4b5a18e11d9fc15f23b5353883a63d838face58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="d4236-102">Практическое руководство. Включение службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="d4236-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="d4236-103">Windows Communication Foundation (WCF) использует службу Windows под названием служба совместного использования портов Net.TCP создать возможность совместного использования портов TCP в нескольких процессах.</span><span class="sxs-lookup"><span data-stu-id="d4236-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="d4236-104">Эта служба устанавливается как часть WCF, но служба не включена по умолчанию в качестве меры предосторожности и поэтому необходимо включить вручную перед первым использованием.</span><span class="sxs-lookup"><span data-stu-id="d4236-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="d4236-105">В настоящем разделе описывается настройка службы совместного использования портов Net.TCP с помощью оснастки консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="d4236-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="d4236-106">После включения служба совместного использования портов Net.TCP и запустить его вручную, см. раздел [как: Настройка службы WCF на совместное использование портов](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) сведения о том, как настроить службу для использования этой службы.</span><span class="sxs-lookup"><span data-stu-id="d4236-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="d4236-107">Образец использует совместное использование порта net.tcp:// см [пример совместного использования портов Net.TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d4236-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="d4236-108">Включение службы совместного использования портов Net.TCP с помощью консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="d4236-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="d4236-109">Из меню «Пуск», откройте консоль управления служб либо откройте окно командной строки и введите `services.msc` или выполнить и введя `services.msc` в поле «Открыть».</span><span class="sxs-lookup"><span data-stu-id="d4236-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="d4236-110">В **имя** столбец из списка служб, щелкните правой кнопкой мыши **доступа к портам NET.TCP**и выберите **свойства** в меню.</span><span class="sxs-lookup"><span data-stu-id="d4236-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="d4236-111">Чтобы включить вручную при запуске службы, в **свойства** выберите **Общие** вкладку и в **тип запуска** выберите вручную, а затем щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d4236-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="d4236-112">Чтобы запустить службу, в области состояния службы, нажмите кнопку **запустить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="d4236-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="d4236-113">Состояние службы теперь будет показано как "Работает".</span><span class="sxs-lookup"><span data-stu-id="d4236-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="d4236-114">Чтобы получить список служб, нажмите кнопку **ОК**и закройте консоль MMC.</span><span class="sxs-lookup"><span data-stu-id="d4236-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4236-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d4236-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4236-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d4236-116">See Also</span></span>  
 [<span data-ttu-id="d4236-117">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="d4236-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="d4236-118">Настройка службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="d4236-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
