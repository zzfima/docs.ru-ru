---
title: Как выполнить Использование нескольких маркеров безопасности одного типа
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 40fc95c905f8923b8aaf2c97fb9dc2b937dfb06f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691353"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="46d3a-102">Как выполнить Использование нескольких маркеров безопасности одного типа</span><span class="sxs-lookup"><span data-stu-id="46d3a-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="46d3a-103">В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 клиентское сообщение содержало только один маркер любого заданного типа.</span><span class="sxs-lookup"><span data-stu-id="46d3a-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="46d3a-104">Теперь клиентские сообщения могут содержать несколько маркеров одного типа.</span><span class="sxs-lookup"><span data-stu-id="46d3a-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="46d3a-105">В этом разделе описывается, как включать в сообщение клиента несколько маркеров одного типа.</span><span class="sxs-lookup"><span data-stu-id="46d3a-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="46d3a-106">Обратите внимание, что настроить таким образом службу невозможно: служба может содержать только один вспомогательный маркер.</span><span class="sxs-lookup"><span data-stu-id="46d3a-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="46d3a-107">Использование нескольких маркеров безопасности одного типа</span><span class="sxs-lookup"><span data-stu-id="46d3a-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="46d3a-108">Создайте пустую коллекцию элементов привязки для заполнения.</span><span class="sxs-lookup"><span data-stu-id="46d3a-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="46d3a-109">Создайте элемент привязки <xref:System.ServiceModel.Channels.SecurityBindingElement>, вызвав метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="46d3a-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="46d3a-110">Создайте коллекцию <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="46d3a-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="46d3a-111">Добавьте в коллекцию маркеры SAML.</span><span class="sxs-lookup"><span data-stu-id="46d3a-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="46d3a-112">Добавьте коллекцию к элементу привязки <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="46d3a-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="46d3a-113">Добавьте элементы привязки в коллекцию элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="46d3a-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="46d3a-114">Верните новую пользовательскую привязку, созданную из коллекции элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="46d3a-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="46d3a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="46d3a-115">Example</span></span>  
 <span data-ttu-id="46d3a-116">Ниже приводится весь метод, описанный в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="46d3a-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="46d3a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="46d3a-117">See also</span></span>
- [<span data-ttu-id="46d3a-118">Архитектура безопасности</span><span class="sxs-lookup"><span data-stu-id="46d3a-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
