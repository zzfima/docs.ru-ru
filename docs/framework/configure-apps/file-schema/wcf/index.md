---
title: "Схем конфигурации WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84e211a0ecd68634a08965a1a4cc1494e0df0713
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="ecfb7-102">Схем конфигурации WCF</span><span class="sxs-lookup"><span data-stu-id="ecfb7-102">WCF Configuration Schema</span></span>
<span data-ttu-id="ecfb7-103">Элементы конфигурации [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] позволяют настроить службу [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] configuration elements enable you to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service and client applications.</span></span> <span data-ttu-id="ecfb7-104">[Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) можно использовать для создания и изменения файлов конфигурации для клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="ecfb7-105">Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="ecfb7-106">В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="ecfb7-107">Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="ecfb7-108">Система конфигурации [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] основана на пространстве имен <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-108">The [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="ecfb7-109">Поэтому можно использовать все стандартные функции, имеющиеся в пространстве имен <xref:System.Configuration>, например блокировку, шифрование и объединение конфигурации для повышения безопасности приложения и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="ecfb7-110">Дополнительные сведения об этих возможностях см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ecfb7-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="ecfb7-111">Шифрование данных конфигурации</span><span class="sxs-lookup"><span data-stu-id="ecfb7-111">Encrypting Configuration Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="ecfb7-112">Блокировка параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="ecfb7-112">Locking Configuration Settings</span></span>](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="ecfb7-113">В этом разделе описаны все возможные значения каждого элемента конфигурации и их взаимодействие с другими элементами конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="ecfb7-114">На следующей иллюстрации показана схема конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-114">The following map illustrates the WCF configuration schema.</span></span>  
  
 <span data-ttu-id="ecfb7-115">![Схема конфигурации WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span><span class="sxs-lookup"><span data-stu-id="ecfb7-115">![WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ecfb7-116">Необходимо защищать разделы конфигурации [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в файлах конфигурации приложения (app.config) с помощью соответствующих списков управления доступом (ACL), чтобы предотвратить потенциальные угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-116">You should protect [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="ecfb7-117">Например, необходимо гарантировать, что иметь доступ или изменять параметры безопасности в привязках приложения или разделе модели службы в файле конфигурации для службы смогут только определенные лица.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecfb7-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="ecfb7-118">In This Section</span></span>  
 [<span data-ttu-id="ecfb7-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ecfb7-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="ecfb7-120">Приводится описание элемента `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="ecfb7-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ecfb7-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="ecfb7-122">Настраивает средство SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="ecfb7-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="ecfb7-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="ecfb7-124">Элемент верхнего уровня для установки параметров при использовании сериализаторов, таких как <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ecfb7-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ecfb7-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ecfb7-125">Related Sections</span></span>  
 [<span data-ttu-id="ecfb7-126">Настройка приложений Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ecfb7-126">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 <span data-ttu-id="ecfb7-127">Описывает настройку служб и клиентов [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecfb7-127">Describes how to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services and clients.</span></span>
