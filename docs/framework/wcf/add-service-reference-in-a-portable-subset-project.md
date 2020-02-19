---
title: Добавление ссылки на службу в проект переносного вложенного набора
ms.date: 03/30/2017
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
ms.openlocfilehash: 8bedfb44523b4f67845d40fadfaa72d64622ba26
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449482"
---
# <a name="add-service-reference-in-a-portable-subset-project"></a><span data-ttu-id="37358-102">Добавление ссылки на службу в проект переносного вложенного набора</span><span class="sxs-lookup"><span data-stu-id="37358-102">Add Service Reference in a Portable Subset Project</span></span>

<span data-ttu-id="37358-103">Переносимые проекты подмножества позволяют программистам сборок .NET поддерживать единое дерево исходного кода и систему сборки, одновременно обеспечивая поддержку нескольких реализаций .NET (Desktop, Silverlight, Windows Phone и Xbox).</span><span class="sxs-lookup"><span data-stu-id="37358-103">Portable subset projects enable .NET assembly programmers to maintain a single source tree and build system while still supporting multiple .NET implementations (desktop, Silverlight, Windows Phone, and Xbox).</span></span> <span data-ttu-id="37358-104">Переносимые проекты подмножества ссылаются только на переносимые библиотеки, которые являются сборками .NET, которые могут использоваться в любой реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="37358-104">Portable subset projects only reference portable libraries that are .NET assemblies that can be used on any .NET implementation.</span></span>
  
## <a name="add-service-reference-details"></a><span data-ttu-id="37358-105">Диалоговое окно «Добавление ссылки на службу»</span><span class="sxs-lookup"><span data-stu-id="37358-105">Add Service Reference Details</span></span>  
 <span data-ttu-id="37358-106">При добавлении ссылки на службу в проект переносного подмножества применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="37358-106">When adding a service reference in a portable subset project the following restrictions are enforced:</span></span>  
  
1. <span data-ttu-id="37358-107">Для <xref:System.Xml.Serialization.XmlSerializer> разрешены только символьные кодирования.</span><span class="sxs-lookup"><span data-stu-id="37358-107">For <xref:System.Xml.Serialization.XmlSerializer>, only literal encodings are allowed.</span></span> <span data-ttu-id="37358-108">Кодировки SOAP приводят к ошибке во время импорта.</span><span class="sxs-lookup"><span data-stu-id="37358-108">SOAP encodings generate an error during import.</span></span>  
  
2. <span data-ttu-id="37358-109">Для служб, использующих сценарии <xref:System.Runtime.Serialization.DataContractSerializer>, предоставляется суррогат контракта данных, гарантирующий что повторно используемые типы находятся в переносимом подмножестве.</span><span class="sxs-lookup"><span data-stu-id="37358-109">For services that use <xref:System.Runtime.Serialization.DataContractSerializer> scenarios, a data contract surrogate is provided to ensure that reused types come only from the portable subset.</span></span>  
  
3. <span data-ttu-id="37358-110">Конечные точки, которые зависят от привязок, неподдерживаемых в переносимых библиотеках (все привязки, кроме <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding>, за исключением привязок потока транзакций, надежных сеансов или кодирования MTOM и соответствующих пользовательских привязок), не учитываются.</span><span class="sxs-lookup"><span data-stu-id="37358-110">Endpoints which rely on bindings not supported in portable libraries (all bindings except <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> without transaction flow, reliable sessions, or MTOM encoding, and equivalent custom bindings) are ignored.</span></span>  
  
4. <span data-ttu-id="37358-111">Перед импортом во всех операциях заголовки сообщений удаляются из всех описаний сообщений.</span><span class="sxs-lookup"><span data-stu-id="37358-111">Message headers are deleted from all message descriptions in all operations before import.</span></span>  
  
5. <span data-ttu-id="37358-112">Непереносимые атрибуты <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>и <xref:System.ServiceModel.TransactionFlowAttribute> удаляются из созданного прокси-кода клиентов.</span><span class="sxs-lookup"><span data-stu-id="37358-112">Non-portable attributes <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, and <xref:System.ServiceModel.TransactionFlowAttribute> are removed from generated client proxy code.</span></span>  
  
6. <span data-ttu-id="37358-113">Непереносимые свойства ProtectionLevel, SessionMode, IsInitiating, IsTerminating удаляются из <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute> и <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="37358-113">Non-portable properties ProtectionLevel, SessionMode, IsInitiating, IsTerminating are removed from <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, and <xref:System.ServiceModel.FaultContractAttribute>.</span></span>  
  
7. <span data-ttu-id="37358-114">Все операции службы создаются в виде асинхронных операций в прокси клиента.</span><span class="sxs-lookup"><span data-stu-id="37358-114">All service operations are generated as asynchronous operations on the client proxy.</span></span>  
  
8. <span data-ttu-id="37358-115">Удаляются конструкторы клиента, которые используют непереносимые типы.</span><span class="sxs-lookup"><span data-stu-id="37358-115">Generated client constructors which use non-portable types are removed.</span></span>  
  
9. <span data-ttu-id="37358-116">Экземпляр <xref:System.Net.CookieContainer> предоставляется в созданном клиенте.</span><span class="sxs-lookup"><span data-stu-id="37358-116">A <xref:System.Net.CookieContainer> instance is exposed on the generated client.</span></span>  
  
10. <span data-ttu-id="37358-117">В начало файла вставляется комментарий, идентифицирующий сборку и версию генератора кода: `// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span><span class="sxs-lookup"><span data-stu-id="37358-117">A comment is inserted at the top of the file identifying the assembly and version of the code generator:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span></span>  
  
11. <span data-ttu-id="37358-118">Интерфейс <xref:System.Runtime.Serialization.ISerializable> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="37358-118">The <xref:System.Runtime.Serialization.ISerializable> interface is not supported.</span></span>  
  
12. <span data-ttu-id="37358-119">Привязки PollingDuplex и Net.Tcp не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="37358-119">Net.Tcp and PollingDuplex bindings are not supported</span></span>  
  
13. <span data-ttu-id="37358-120">Класс <xref:System.Runtime.Serialization.DataContractSerializer> всегда будет использоваться для отработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="37358-120">The <xref:System.Runtime.Serialization.DataContractSerializer> will always be used for faults.</span></span>  
  
14. <span data-ttu-id="37358-121">Свойство <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> не поддерживается в проектах переносимого подмножества.</span><span class="sxs-lookup"><span data-stu-id="37358-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is not supported in portable subset projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37358-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="37358-122">See also</span></span>

- [<span data-ttu-id="37358-123">Обращение к службам с помощью клиента WCF</span><span class="sxs-lookup"><span data-stu-id="37358-123">Accessing Services Using a WCF Client</span></span>](accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="37358-124">Переносимая библиотека классов</span><span class="sxs-lookup"><span data-stu-id="37358-124">Portable Class Library</span></span>](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
