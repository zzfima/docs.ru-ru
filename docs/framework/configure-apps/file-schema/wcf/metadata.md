---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: c0c9848d073c799e1f97dd79b375848dfab71e99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191488"
---
# <a name="metadata"></a><span data-ttu-id="b2f6d-101">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="b2f6d-101">\<metadata></span></span>
<span data-ttu-id="b2f6d-102">Задает способ обработки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-102">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="b2f6d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b2f6d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b2f6d-104">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="b2f6d-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f6d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2f6d-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2f6d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2f6d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b2f6d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2f6d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2f6d-108">Attributes</span></span>  
 <span data-ttu-id="b2f6d-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2f6d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2f6d-110">Child Elements</span></span>  
  
|<span data-ttu-id="b2f6d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2f6d-111">Element</span></span>|<span data-ttu-id="b2f6d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b2f6d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2f6d-113">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="b2f6d-113">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="b2f6d-114">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="b2f6d-115">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-115">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="b2f6d-116">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b2f6d-116">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="b2f6d-117">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-117">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="b2f6d-118">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-118">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="b2f6d-119">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-119">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="b2f6d-120">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-120">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2f6d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2f6d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b2f6d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2f6d-122">Element</span></span>|<span data-ttu-id="b2f6d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="b2f6d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2f6d-124">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="b2f6d-124">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="b2f6d-125">В разделе client определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-125">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2f6d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b2f6d-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="b2f6d-127">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="b2f6d-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="b2f6d-128">Клиенты</span><span class="sxs-lookup"><span data-stu-id="b2f6d-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
