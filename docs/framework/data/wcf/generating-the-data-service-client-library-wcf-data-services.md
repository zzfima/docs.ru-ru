---
title: Создание библиотеки клиентов службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 14ea550715c1b224945137f123eed3b53e56cead
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918641"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="8839f-102">Создание библиотеки клиентов службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="8839f-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="8839f-103">Служба данных, реализующая интерфейс [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] , может возвращать документ метаданных службы, описывающий модель данных, предоставляемую [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналом.</span><span class="sxs-lookup"><span data-stu-id="8839f-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="8839f-104">Дополнительные сведения см. в [разделе OData: Документ](https://go.microsoft.com/fwlink/?LinkId=186070)метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="8839f-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="8839f-105">Для добавления ссылки на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]службу на основе можно использовать диалоговое окно Добавление ссылки на службу в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8839f-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="8839f-106">При использовании этого средства для добавления ссылки на метаданные, возвращаемые [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналом в клиентский проект, выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8839f-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="8839f-107">Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="8839f-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8839f-108">Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX.</span><span class="sxs-lookup"><span data-stu-id="8839f-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="8839f-109">Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8839f-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="8839f-110">Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="8839f-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="8839f-111">Дополнительные сведения см. на [ \[странице MC-EDMX\]: Спецификация формата](https://go.microsoft.com/fwlink/?LinkID=178833) упаковки для служб данных EDM</span><span class="sxs-lookup"><span data-stu-id="8839f-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
- <span data-ttu-id="8839f-112">Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="8839f-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="8839f-113">Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM.</span><span class="sxs-lookup"><span data-stu-id="8839f-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="8839f-114">Дополнительные сведения см. в разделе [Обзор служб объектов (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8839f-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="8839f-115">Формирует классы данных типов модели данных, обнаруженных в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="8839f-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="8839f-116">Добавляет в проект ссылку на сборку `System.Data.Services.Client`.</span><span class="sxs-lookup"><span data-stu-id="8839f-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="8839f-117">Дополнительные сведения см. в разделе [Практическое руководство. Добавьте ссылку](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)на службу данных.</span><span class="sxs-lookup"><span data-stu-id="8839f-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="8839f-118">Классы клиентской службы данных также можно создать с помощью средства [DataSvcUtil. exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) из командной строки.</span><span class="sxs-lookup"><span data-stu-id="8839f-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="8839f-119">Дополнительные сведения см. в разделе [Практическое руководство. Создание классов](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)клиентской службы данных вручную.</span><span class="sxs-lookup"><span data-stu-id="8839f-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="8839f-120">Сопоставление клиентских типов данных</span><span class="sxs-lookup"><span data-stu-id="8839f-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="8839f-121">При использовании диалогового окна **Добавление ссылки на службу** в Visual Studio или `DataSvcUtil.exe` средства для создания клиентских классов данных, основанных на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канале, типы данных .NET Framework сопоставляются с типами-примитивами из модели данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8839f-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="8839f-122">Тип модели данных</span><span class="sxs-lookup"><span data-stu-id="8839f-122">Data model type</span></span>|<span data-ttu-id="8839f-123">Тип данных .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8839f-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="8839f-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="8839f-124"><xref:System.Byte> `[]`</span></span>|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 <span data-ttu-id="8839f-125">Дополнительные сведения см. в [разделе OData: Примитивные типы](https://go.microsoft.com/fwlink/?LinkId=186072)данных.</span><span class="sxs-lookup"><span data-stu-id="8839f-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8839f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8839f-126">See also</span></span>

- [<span data-ttu-id="8839f-127">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="8839f-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="8839f-128">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="8839f-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
