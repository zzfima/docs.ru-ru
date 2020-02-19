---
title: Схема конфигурации WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 866b0639f4391e1898bbe36e458df87e3c24bfff
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448663"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="3449b-102">Схема конфигурации WCF</span><span class="sxs-lookup"><span data-stu-id="3449b-102">WCF Configuration Schema</span></span>
<span data-ttu-id="3449b-103">Элементы конфигурации Windows Communication Foundation (WCF) позволяют настроить службу WCF и клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="3449b-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="3449b-104">[Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) можно использовать для создания и изменения файлов конфигурации для клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="3449b-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="3449b-105">Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом.</span><span class="sxs-lookup"><span data-stu-id="3449b-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="3449b-106">В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="3449b-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="3449b-107">Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="3449b-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="3449b-108">Система конфигурации WCF основана на пространстве имен <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="3449b-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="3449b-109">Поэтому можно использовать все стандартные возможности, имеющиеся в пространстве имен <xref:System.Configuration>, например блокировку, шифрование и объединение конфигурации для повышения безопасности приложения и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3449b-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="3449b-110">Дополнительные сведения об этих возможностях см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3449b-110">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="3449b-111">[Шифрование данных конфигурации](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3449b-111">[Encrypting Configuration Information](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="3449b-112">[Блокировка параметров конфигурации](https://docs.microsoft.com/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3449b-112">[Locking Configuration Settings](https://docs.microsoft.com/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="3449b-113">В этом разделе описаны все возможные значения каждого элемента конфигурации и их взаимодействие с другими элементами конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="3449b-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="3449b-114">Следующая схема иллюстрирует схему конфигурации WCF:</span><span class="sxs-lookup"><span data-stu-id="3449b-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![Схема, на которой показана схема конфигурации WCF.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> <span data-ttu-id="3449b-116">Необходимо защитить разделы конфигурации WCF в файлах конфигурации приложения (App. config) с соответствующими списками управления доступом (ACL), чтобы предотвратить потенциальные угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="3449b-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="3449b-117">Например, необходимо гарантировать, что иметь доступ или изменять параметры безопасности в привязках приложения или разделе модели службы в файле конфигурации для службы смогут только определенные лица.</span><span class="sxs-lookup"><span data-stu-id="3449b-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3449b-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="3449b-118">In This Section</span></span>  
 [<span data-ttu-id="3449b-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3449b-119">\<system.serviceModel></span></span>](system-servicemodel.md)  
 <span data-ttu-id="3449b-120">Приводится описание элемента `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="3449b-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="3449b-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="3449b-121">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)  
 <span data-ttu-id="3449b-122">Настраивает средство SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="3449b-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="3449b-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="3449b-123">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
 <span data-ttu-id="3449b-124">Элемент верхнего уровня для установки параметров при использовании сериализаторов, таких как <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3449b-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3449b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3449b-125">Related Sections</span></span>  
 [<span data-ttu-id="3449b-126">Настройка приложений Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3449b-126">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="3449b-127">Описывает настройку служб и клиентов WCF.</span><span class="sxs-lookup"><span data-stu-id="3449b-127">Describes how to configure WCF services and clients.</span></span>
