---
title: Практическое руководство. Добавление ссылки на службу данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: a8dcc01fb7a564a363cabed6a22738cd520d317f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356235"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="31b7d-102">Практическое руководство. Добавление ссылки на службу данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="31b7d-102">How to: Add a Data Service Reference (WCF Data Services)</span></span>
<span data-ttu-id="31b7d-103">Можно использовать **добавить ссылку на службу** диалогового окна в Visual Studio, чтобы добавить ссылку на [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31b7d-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="31b7d-104">Это позволяет упростить доступ к службе данных в клиентском приложении, разрабатываемом в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31b7d-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="31b7d-105">По завершении этой процедуры формируются классы данных на основе метаданных, полученных от службы данных.</span><span class="sxs-lookup"><span data-stu-id="31b7d-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="31b7d-106">Дополнительные сведения см. в разделе [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="31b7d-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>  
  
### <a name="to-add-a-data-service-reference"></a><span data-ttu-id="31b7d-107">Добавление ссылки на службу данных</span><span class="sxs-lookup"><span data-stu-id="31b7d-107">To add a data service reference</span></span>  
  
1.  <span data-ttu-id="31b7d-108">Если служба данных не является частью решения и пока не запущена, запустите ее и отметьте ее URI. (Необязательно.)</span><span class="sxs-lookup"><span data-stu-id="31b7d-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>  
  
2.  <span data-ttu-id="31b7d-109">Щелкните правой кнопкой мыши клиентский проект и выберите **добавить ссылку на службу**.</span><span class="sxs-lookup"><span data-stu-id="31b7d-109">Right-click the client project and then select **Add Service Reference**.</span></span>  
  
3.  <span data-ttu-id="31b7d-110">Если служба данных является частью текущего решения, нажмите кнопку **Discover**.</span><span class="sxs-lookup"><span data-stu-id="31b7d-110">If the data service is part of the current solution, click **Discover**.</span></span>  
  
     <span data-ttu-id="31b7d-111">- или -</span><span class="sxs-lookup"><span data-stu-id="31b7d-111">-or-</span></span>  
  
     <span data-ttu-id="31b7d-112">В **адрес** текстовом поле Введите базовый URL-адрес службы данных, таких как `http://localhost:1234/Northwind.svc`, а затем нажмите кнопку **Go**.</span><span class="sxs-lookup"><span data-stu-id="31b7d-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>  
  
4.  <span data-ttu-id="31b7d-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="31b7d-113">Click **OK**.</span></span>  
  
     <span data-ttu-id="31b7d-114">При этом добавляется новый файл кода, содержащий классы данных, которые используются для обращения и взаимодействия с ресурсами службы данных как с объектами.</span><span class="sxs-lookup"><span data-stu-id="31b7d-114">This adds a new code file that contains the data classes that are used to access and interact with data service resources as objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b7d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="31b7d-115">See Also</span></span>  
 [<span data-ttu-id="31b7d-116">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="31b7d-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
