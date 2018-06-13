---
title: Практическое руководство. Экспорт метаданных из конечных точек службы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: 9235498956f53d69b3024d1db023f3eb0908d2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491547"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="4042a-102">Практическое руководство. Экспорт метаданных из конечных точек службы</span><span class="sxs-lookup"><span data-stu-id="4042a-102">How to: Export Metadata from Service Endpoints</span></span>
<span data-ttu-id="4042a-103">В этом разделе объясняется, как экспортировать метаданные из конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="4042a-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="4042a-104">Экспорт метаданных из конечных точек службы</span><span class="sxs-lookup"><span data-stu-id="4042a-104">To export metadata from service endpoints</span></span>  
  
1.  <span data-ttu-id="4042a-105">Создайте новый проект "Консольное приложение" в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4042a-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="4042a-106">Добавьте в созданный внутри метода main() файл Program.cs приведенный в описании следующих шагов код.</span><span class="sxs-lookup"><span data-stu-id="4042a-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2.  <span data-ttu-id="4042a-107">Создайте таблицу <xref:System.ServiceModel.Description.WsdlExporter>.</span><span class="sxs-lookup"><span data-stu-id="4042a-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3.  <span data-ttu-id="4042a-108">Присвойте свойству <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> одно из значений из перечисления <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="4042a-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="4042a-109">В этом примере свойству задается значение <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>, что соответствует WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="4042a-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4.  <span data-ttu-id="4042a-110">Создайте массив объектов <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="4042a-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5.  <span data-ttu-id="4042a-111">Экспортируйте метаданные для каждой конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="4042a-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6.  <span data-ttu-id="4042a-112">Убедитесь, что в процессе экспорта не произошло ошибок, и извлеките метаданные.</span><span class="sxs-lookup"><span data-stu-id="4042a-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7.  <span data-ttu-id="4042a-113">После этого можно использовать метаданные, например записать их в файл, вызвав метод <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>.</span><span class="sxs-lookup"><span data-stu-id="4042a-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4042a-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4042a-114">Example</span></span>  
 <span data-ttu-id="4042a-115">Ниже приведен полный код этого примера.</span><span class="sxs-lookup"><span data-stu-id="4042a-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4042a-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4042a-116">Compiling the Code</span></span>  
 <span data-ttu-id="4042a-117">При компиляции файла Program.cs необходимо сослаться на System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="4042a-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4042a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4042a-118">See Also</span></span>  
 [<span data-ttu-id="4042a-119">Общие сведения об архитектуре метаданных</span><span class="sxs-lookup"><span data-stu-id="4042a-119">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [<span data-ttu-id="4042a-120">Использование метаданных</span><span class="sxs-lookup"><span data-stu-id="4042a-120">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="4042a-121">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="4042a-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
