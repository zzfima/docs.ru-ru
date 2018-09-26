---
title: Практическое руководство. Использование нескольких маркеров безопасности одного типа
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
ms.openlocfilehash: 9d1dab0f4da82e4db96471f0a8cf25c32bd5eced
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47110923"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="1aac6-102">Практическое руководство. Использование нескольких маркеров безопасности одного типа</span><span class="sxs-lookup"><span data-stu-id="1aac6-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="1aac6-103">В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 клиентское сообщение содержало только один маркер любого заданного типа.</span><span class="sxs-lookup"><span data-stu-id="1aac6-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="1aac6-104">Теперь клиентские сообщения могут содержать несколько маркеров одного типа.</span><span class="sxs-lookup"><span data-stu-id="1aac6-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="1aac6-105">В этом разделе описывается, как включать в сообщение клиента несколько маркеров одного типа.</span><span class="sxs-lookup"><span data-stu-id="1aac6-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="1aac6-106">Обратите внимание, что настроить таким образом службу невозможно: служба может содержать только один вспомогательный маркер.</span><span class="sxs-lookup"><span data-stu-id="1aac6-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="1aac6-107">Использование нескольких маркеров безопасности одного типа</span><span class="sxs-lookup"><span data-stu-id="1aac6-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="1aac6-108">Создайте пустую коллекцию элементов привязки для заполнения.</span><span class="sxs-lookup"><span data-stu-id="1aac6-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="1aac6-109">Создайте элемент привязки <xref:System.ServiceModel.Channels.SecurityBindingElement>, вызвав метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="1aac6-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="1aac6-110">Создайте коллекцию <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="1aac6-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="1aac6-111">Добавьте в коллекцию маркеры SAML.</span><span class="sxs-lookup"><span data-stu-id="1aac6-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="1aac6-112">Добавьте коллекцию к элементу привязки <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="1aac6-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="1aac6-113">Добавьте элементы привязки в коллекцию элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="1aac6-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="1aac6-114">Верните новую пользовательскую привязку, созданную из коллекции элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="1aac6-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="1aac6-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1aac6-115">Example</span></span>  
 <span data-ttu-id="1aac6-116">Ниже приводится весь метод, описанный в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="1aac6-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="1aac6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1aac6-117">See Also</span></span>  
 [<span data-ttu-id="1aac6-118">Архитектура безопасности</span><span class="sxs-lookup"><span data-stu-id="1aac6-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
