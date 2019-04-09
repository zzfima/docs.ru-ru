---
title: Программа командной строки настройки модели служб COM+ (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 6d0967355e64640e0fd5c81f04a5bf4f33c7b3f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158669"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="c8e3c-102">Программа командной строки настройки модели служб COM+ (ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="c8e3c-102">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>
<span data-ttu-id="c8e3c-103">Программа командной строки для настройки модели служб COM+ (ComSvcConfig.exe) позволяет настраивать интерфейсы COM+, которые нужно предоставить как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-103">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8e3c-104">Syntax</span></span>  
  
```  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="c8e3c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8e3c-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8e3c-106">Для использования ComSvcConfig.exe на компьютере под управлением ОС Windows Vista требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-106">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="c8e3c-107">Это средство можно найти в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="c8e3c-107">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="c8e3c-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="c8e3c-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
 <span data-ttu-id="c8e3c-109">Дополнительные сведения о ComSvcConfig.exe см. в разделе [как: Используйте средство настройки модели служб COM +](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="c8e3c-109">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="c8e3c-110">В следующей таблице представлены режимы, которые могут использоваться с ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-110">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="c8e3c-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="c8e3c-111">Option</span></span>|<span data-ttu-id="c8e3c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e3c-112">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="c8e3c-113">Устанавливает конфигурацию для интерфейса COM+ для интеграции Service Model.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-113">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="c8e3c-114">Краткая форма: `/i`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-114">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="c8e3c-115">Удаляет конфигурацию для интерфейса COM+ из интеграции Service Model.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-115">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="c8e3c-116">Краткая форма: `/u`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-116">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="c8e3c-117">Отображает сведения о приложениях и компонентах COM+, которые имеют интерфейсы, настроенные для интеграции Service Model.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-117">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="c8e3c-118">Краткая форма: `/l`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-118">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="c8e3c-119">В следующей таблице представлены флаги, которые могут использоваться с ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-119">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="c8e3c-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="c8e3c-120">Option</span></span>|<span data-ttu-id="c8e3c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e3c-121">Description</span></span>|  
|------------|-----------------|  
|`/application:` <span data-ttu-id="c8e3c-122">\<*ApplicationID* &#124; *ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="c8e3c-122">\<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="c8e3c-123">Позволяет указать приложение COM+ для настройки.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-123">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="c8e3c-124">Краткая форма: `/a`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-124">Short form `/a`.</span></span>|  
|`/contract:` <span data-ttu-id="c8e3c-125">\<*ClassID* &#124; *ProgID* &#124; \*,*InterfaceID* &#124; *InterfaceName*    &#124; \*\></span><span class="sxs-lookup"><span data-stu-id="c8e3c-125">\<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="c8e3c-126">Позволяет указать компонент и интерфейс COM+, которые будут настроены в качестве контракта для службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-126">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="c8e3c-127">Краткая форма: `/c`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-127">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="c8e3c-128">Хотя подстановочный знак (\*) может использоваться для указания имен компонента и интерфейса, мы рекомендуем не использовать его, так как могут быть предоставлены интерфейсы, которые вы не планировали.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-128">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|`/hosting:` <span data-ttu-id="c8e3c-129">\<*complus*  &#124; *was*\></span><span class="sxs-lookup"><span data-stu-id="c8e3c-129">\<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="c8e3c-130">Позволяет указать необходимость использования режима размещения COM+ или режима размещения на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-130">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="c8e3c-131">Краткая форма: `/h`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-131">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="c8e3c-132">Для использования режима размещения COM+ требуется явная активация приложения COM+.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-132">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="c8e3c-133">Использование режима размещения на веб-сервере позволяет автоматически активировать приложение COM+ при необходимости.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-133">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="c8e3c-134">Если приложение COM+ является библиотечным приложением, оно выполняется в процессе IIS.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-134">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="c8e3c-135">Если приложение COM+ является серверным приложением, оно выполняется в процессе Dllhost.exe.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-135">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|`/webSite:` <span data-ttu-id="c8e3c-136">\<*WebsiteName*\></span><span class="sxs-lookup"><span data-stu-id="c8e3c-136">\<*WebsiteName*\></span></span>|<span data-ttu-id="c8e3c-137">Позволяет указать веб-сайт для размещения при использовании режима размещения на веб-сервере (см. флаг `/hosting`).</span><span class="sxs-lookup"><span data-stu-id="c8e3c-137">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="c8e3c-138">Краткая форма: `/w`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-138">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="c8e3c-139">Если веб-сайт не указан, используется веб-сайт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-139">If no Web site is specified, the default Web site is used.</span></span>|  
|`/webDirectory:` <span data-ttu-id="c8e3c-140">\<*WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="c8e3c-140">\<*WebDirectoryName*\></span></span>|<span data-ttu-id="c8e3c-141">Позволяет указать виртуальный каталог для размещения при использовании режима размещения на веб-сервере (см. флаг `/hosting`).</span><span class="sxs-lookup"><span data-stu-id="c8e3c-141">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="c8e3c-142">Краткая форма: `/d`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-142">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="c8e3c-143">Добавляет конечную точку службы обмена метаданными в конфигурацию службы по умолчанию для поддержки клиентов, которым требуется извлечь определение контракта из службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-143">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="c8e3c-144">Краткая форма: `/x`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-144">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="c8e3c-145">Отображает информацию о приложении, компоненте и интерфейсе в виде идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-145">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="c8e3c-146">Краткая форма: `/k`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-146">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="c8e3c-147">Подавляет отображение логотипа ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-147">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="c8e3c-148">Краткая форма: `/n`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-148">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="c8e3c-149">Выводит все предупреждения или информационный текст в дополнение к любым обнаруженным ошибкам.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-149">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="c8e3c-150">Краткая форма: `/v`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-150">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="c8e3c-151">Отображает сообщение об использовании.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-151">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="c8e3c-152">Краткая форма: `/?`.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-152">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="c8e3c-153">Создает конфигурацию службы, если указанный интерфейс включает одну или несколько сигнатур метода, которые могут быть предоставлены для использования.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-153">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="c8e3c-154">Во время инициализации службы совместимые методы отображаются как операции над контрактом службы, а несовместимые методы игнорируются и исключаются из контракта службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-154">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="c8e3c-155">Если данный флаг отсутствует, средство не создает конфигурацию службы, когда указанный интерфейс включает один или несколько несовместимых методов.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-155">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="c8e3c-156">Примеры</span><span class="sxs-lookup"><span data-stu-id="c8e3c-156">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="c8e3c-157">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e3c-157">Description</span></span>  
 <span data-ttu-id="c8e3c-158">В следующем примере с помощью режима размещения COM+ выполняется добавление интерфейса `IFinances` компонента `ItemOrders.IFinancial` (из приложения COM+ OnlineStore) в набор интерфейсов, предоставляемых как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-158">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="c8e3c-159">В дополнение к любым обнаруженным ошибкам выводятся все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-159">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c8e3c-160">Код</span><span class="sxs-lookup"><span data-stu-id="c8e3c-160">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="c8e3c-161">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e3c-161">Description</span></span>  
 <span data-ttu-id="c8e3c-162">В следующем примере с помощью режима размещения на веб-сервере выполняется добавление интерфейса `IStockLevels` компонента `ItemInventory.Warehouse` (из приложения COM+ OnlineWarehouse) в набор интерфейсов, предоставляемых как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-162">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="c8e3c-163">Веб-служба размещается в виртуальном каталоге OnlineWarehouse в IIS.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-163">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c8e3c-164">Код</span><span class="sxs-lookup"><span data-stu-id="c8e3c-164">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="c8e3c-165">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e3c-165">Description</span></span>  
 <span data-ttu-id="c8e3c-166">В следующем примере выполняется удаление интерфейса `IFinances` компонента `ItemOrders.Financial` (из приложения COM+ OnlineStore) из набора интерфейсов, предоставляемых как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-166">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c8e3c-167">Код</span><span class="sxs-lookup"><span data-stu-id="c8e3c-167">Code</span></span>  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="c8e3c-168">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e3c-168">Description</span></span>  
 <span data-ttu-id="c8e3c-169">В следующем примере выводится список предоставляемых в данный момент интерфейсов, размещенных в COM+, а также соответствующий адрес и сведения о привязке для приложения COM+ OnlineStore на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c8e3c-169">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c8e3c-170">Код</span><span class="sxs-lookup"><span data-stu-id="c8e3c-170">Code</span></span>  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8e3c-171">См. также</span><span class="sxs-lookup"><span data-stu-id="c8e3c-171">See also</span></span>

- [<span data-ttu-id="c8e3c-172">Практическое руководство. Использование программы командной строки настройки модели служб COM+</span><span class="sxs-lookup"><span data-stu-id="c8e3c-172">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
