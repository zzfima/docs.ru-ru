---
title: Схем конфигурации WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 37330b571553bb5e8f17ffad85faafbcaf19d217
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041288"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="7af6c-102">Схем конфигурации WCF</span><span class="sxs-lookup"><span data-stu-id="7af6c-102">WCF Configuration Schema</span></span>
<span data-ttu-id="7af6c-103">Элементы конфигурации Windows Communication Foundation (WCF) позволяют настроить службу WCF и клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="7af6c-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="7af6c-104">[Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) можно использовать для создания и изменения файлов конфигурации для клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="7af6c-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="7af6c-105">Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом.</span><span class="sxs-lookup"><span data-stu-id="7af6c-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="7af6c-106">В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="7af6c-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="7af6c-107">Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="7af6c-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="7af6c-108">Система конфигурации WCF основана на <xref:System.Configuration> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="7af6c-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="7af6c-109">Поэтому можно использовать все стандартные возможности, имеющиеся в пространстве имен <xref:System.Configuration>, например блокировку, шифрование и объединение конфигурации для повышения безопасности приложения и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7af6c-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="7af6c-110">Дополнительные сведения об этих возможностях см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7af6c-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="7af6c-111">Шифрование данных конфигурации</span><span class="sxs-lookup"><span data-stu-id="7af6c-111">Encrypting Configuration Information</span></span>](https://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="7af6c-112">Блокировка параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="7af6c-112">Locking Configuration Settings</span></span>](https://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="7af6c-113">В этом разделе описаны все возможные значения каждого элемента конфигурации и их взаимодействие с другими элементами конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="7af6c-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="7af6c-114">Следующая схема иллюстрирует схему конфигурации WCF:</span><span class="sxs-lookup"><span data-stu-id="7af6c-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![Схема, на которой показана схема конфигурации WCF.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> <span data-ttu-id="7af6c-116">Необходимо защитить разделы конфигурации WCF в файлах конфигурации приложения (App. config) с соответствующими списками управления доступом (ACL), чтобы предотвратить потенциальные угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="7af6c-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="7af6c-117">Например, необходимо гарантировать, что иметь доступ или изменять параметры безопасности в привязках приложения или разделе модели службы в файле конфигурации для службы смогут только определенные лица.</span><span class="sxs-lookup"><span data-stu-id="7af6c-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7af6c-118">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7af6c-118">In This Section</span></span>  
 [<span data-ttu-id="7af6c-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7af6c-119">\<system.serviceModel></span></span>](system-servicemodel.md)  
 <span data-ttu-id="7af6c-120">Приводится описание элемента `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="7af6c-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="7af6c-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="7af6c-121">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)  
 <span data-ttu-id="7af6c-122">Настраивает средство SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="7af6c-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="7af6c-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="7af6c-123">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
 <span data-ttu-id="7af6c-124">Элемент верхнего уровня для установки параметров при использовании сериализаторов, таких как <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7af6c-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7af6c-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7af6c-125">Related Sections</span></span>  
 [<span data-ttu-id="7af6c-126">Настройка приложений Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7af6c-126">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="7af6c-127">Описывает настройку служб и клиентов WCF.</span><span class="sxs-lookup"><span data-stu-id="7af6c-127">Describes how to configure WCF services and clients.</span></span>
