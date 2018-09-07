---
title: Практическое руководство. Добавление ссылки на службу данных (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084641"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="1c4e9-102">Практическое: Добавление ссылки на службу данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="1c4e9-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="1c4e9-103">Можно использовать **Add Service Reference** диалоговое окно в Visual Studio для добавления ссылки на службы WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="1c4e9-104">Это позволяет упростить доступ к службе данных в клиентском приложении, разрабатываемом в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="1c4e9-105">По завершении этой процедуры формируются классы данных на основе метаданных, полученных от службы данных.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="1c4e9-106">Дополнительные сведения см. в разделе [Создание клиентской библиотеки службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1c4e9-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="1c4e9-107">Добавьте ссылку на службу данных</span><span class="sxs-lookup"><span data-stu-id="1c4e9-107">Add a data service reference</span></span>

1. <span data-ttu-id="1c4e9-108">Если служба данных не является частью решения и пока не запущена, запустите ее и отметьте ее URI. (Необязательно.)</span><span class="sxs-lookup"><span data-stu-id="1c4e9-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="1c4e9-109">В Visual Studio в **обозревателе решений**, щелкните правой кнопкой мыши клиентский проект и выберите **добавить** > **ссылки на службу**.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="1c4e9-110">Если служба данных является частью текущего решения, нажмите кнопку **Discover**.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="1c4e9-111">- или -</span><span class="sxs-lookup"><span data-stu-id="1c4e9-111">-or-</span></span>

     <span data-ttu-id="1c4e9-112">В **адрес** текстовом поле Введите базовый URL-адрес службы данных, такие как `http://localhost:1234/Northwind.svc`, а затем нажмите кнопку **Go**.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="1c4e9-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-113">Select **OK**.</span></span>

     <span data-ttu-id="1c4e9-114">В проект добавляется новый файл кода, содержащий классы данных, доступа и работе с ресурсами службы данных.</span><span class="sxs-lookup"><span data-stu-id="1c4e9-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c4e9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1c4e9-115">See also</span></span>

- [<span data-ttu-id="1c4e9-116">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="1c4e9-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)