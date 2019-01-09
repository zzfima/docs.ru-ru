---
title: '&lt;Метаданные&gt;'
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 119cd4d5b63f8d957bc6db9dd6aabdf9e2beeb64
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147373"
---
# <a name="ltmetadatagt"></a><span data-ttu-id="47457-102">&lt;Метаданные&gt;</span><span class="sxs-lookup"><span data-stu-id="47457-102">&lt;metadata&gt;</span></span>
<span data-ttu-id="47457-103">Задает способ обработки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="47457-103">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="47457-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="47457-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="47457-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="47457-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47457-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47457-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47457-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47457-107">Attributes and Elements</span></span>  
 <span data-ttu-id="47457-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47457-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47457-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47457-109">Attributes</span></span>  
 <span data-ttu-id="47457-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="47457-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47457-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47457-111">Child Elements</span></span>  
  
|<span data-ttu-id="47457-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="47457-112">Element</span></span>|<span data-ttu-id="47457-113">Описание</span><span class="sxs-lookup"><span data-stu-id="47457-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47457-114">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="47457-114">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="47457-115">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="47457-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="47457-116">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="47457-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="47457-117">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="47457-117">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="47457-118">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="47457-118">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="47457-119">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="47457-119">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="47457-120">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="47457-120">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="47457-121">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="47457-121">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47457-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47457-122">Parent Elements</span></span>  
  
|<span data-ttu-id="47457-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="47457-123">Element</span></span>|<span data-ttu-id="47457-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="47457-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47457-125">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="47457-125">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="47457-126">В разделе client определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="47457-126">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47457-127">См. также</span><span class="sxs-lookup"><span data-stu-id="47457-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="47457-128">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="47457-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="47457-129">Клиенты</span><span class="sxs-lookup"><span data-stu-id="47457-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
