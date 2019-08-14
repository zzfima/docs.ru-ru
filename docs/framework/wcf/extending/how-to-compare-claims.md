---
title: Практическое руководство. Сравнение утверждений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
ms.openlocfilehash: e2d3d33900dd894eea77420aac444ebde0df9a43
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68970767"
---
# <a name="how-to-compare-claims"></a><span data-ttu-id="88990-102">Практическое руководство. Сравнение утверждений</span><span class="sxs-lookup"><span data-stu-id="88990-102">How to: Compare Claims</span></span>

<span data-ttu-id="88990-103">Инфраструктура модели удостоверений в Windows Communication Foundation (WCF) используется для выполнения проверки авторизации.</span><span class="sxs-lookup"><span data-stu-id="88990-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) is used to perform authorization checking.</span></span> <span data-ttu-id="88990-104">По существу общей задачей является сравнение утверждений в контексте авторизации с утверждениями, необходимыми для выполнения затребованного действия или доступа к затребованному ресурсу.</span><span class="sxs-lookup"><span data-stu-id="88990-104">As such, a common task is to compare claims in the authorization context to the claims required to perform the requested action or access the requested resource.</span></span> <span data-ttu-id="88990-105">В этом разделе описывается сравнение утверждений, включая встроенные и пользовательские типы утверждений.</span><span class="sxs-lookup"><span data-stu-id="88990-105">This topic describes how to compare claims, including built-in and custom claim types.</span></span> <span data-ttu-id="88990-106">Дополнительные сведения о инфраструктуре модели удостоверений см. [в статье Управление утверждениями и авторизацией с помощью модели удостоверений](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="88990-106">For more information about the Identity Model infrastructure, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="88990-107">При сравнении утверждений сравниваются три элемента одного утверждения (тип, право и ресурс) с аналогичными элементами другого утверждения, чтобы определить, одинаковы ли они.</span><span class="sxs-lookup"><span data-stu-id="88990-107">Claim comparison involves comparing the three parts of a claim (type, right, and resource) against the same parts in another claim to see if they are equal.</span></span> <span data-ttu-id="88990-108">См. следующий пример.</span><span class="sxs-lookup"><span data-stu-id="88990-108">See the following example.</span></span>

[!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
[!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]

<span data-ttu-id="88990-109">Оба утверждения будут иметь тип имени <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, право свойства <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> и ресурс строки «someone».</span><span class="sxs-lookup"><span data-stu-id="88990-109">Both claims have a claim type of <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource of the string "someone".</span></span> <span data-ttu-id="88990-110">Поскольку все три элемента утверждения одинаковы, сами утверждения одинаковы.</span><span class="sxs-lookup"><span data-stu-id="88990-110">As all three parts of the claim are equal, the claims themselves are equal.</span></span>

<span data-ttu-id="88990-111">Встроенные типы утверждений сравниваются с помощью метода <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="88990-111">The built-in claim types are compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="88990-112">При необходимости используется код сравнения, зависящий от утверждений.</span><span class="sxs-lookup"><span data-stu-id="88990-112">Claim-specific comparison code is used where necessary.</span></span> <span data-ttu-id="88990-113">Например, пусть заданы следующие два утверждения с именем участника-пользователя:</span><span class="sxs-lookup"><span data-stu-id="88990-113">For example, given the following two user principal name (UPN) claims:</span></span>

[!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
[!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]

<span data-ttu-id="88990-114">код сравнения в <xref:System.IdentityModel.Claims.Claim.Equals%2A> методе возвращает `true`, предполагая `example\someone` , что он идентифицирует того же пользователя доменаsomeone@example.com, что и "".</span><span class="sxs-lookup"><span data-stu-id="88990-114">the comparison code in the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method returns `true`, assuming `example\someone` identifies the same domain user as "someone@example.com".</span></span>

<span data-ttu-id="88990-115">Пользовательские типы утверждений также могут сравниваться с помощью метода <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="88990-115">Custom claim types can also be compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="88990-116">Однако в тех случаях, когда тип, возвращенный свойством <xref:System.IdentityModel.Claims.Claim.Resource%2A> утверждения, несколько отличается от типа-примитива, метод <xref:System.IdentityModel.Claims.Claim.Equals%2A> возвращает значение `true`, только если значения, возвращенные свойствами `Resource`, одинаковы для каждого метода <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="88990-116">However, in cases where the type returned by the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property of the claim is something other than a primitive type, the <xref:System.IdentityModel.Claims.Claim.Equals%2A> returns `true` only if the values returned by the `Resource` properties are equal according to the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="88990-117">В других случаях пользовательский тип, возвращенный свойством `Resource`, должен переопределить методы <xref:System.IdentityModel.Claims.Claim.Equals%2A> и <xref:System.Object.GetHashCode%2A>, чтобы выполнить любую необходимую пользовательскую обработку.</span><span class="sxs-lookup"><span data-stu-id="88990-117">In cases where this is not appropriate, the custom type returned by the `Resource` property should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods to perform whatever custom processing is necessary.</span></span>

## <a name="comparing-built-in-claims"></a><span data-ttu-id="88990-118">Сравнение встроенных утверждений</span><span class="sxs-lookup"><span data-stu-id="88990-118">Comparing built-in claims</span></span>

1. <span data-ttu-id="88990-119">Пусть заданы два экземпляра класса <xref:System.IdentityModel.Claims.Claim>. Используйте метод <xref:System.IdentityModel.Claims.Claim.Equals%2A> для выполнения сравнения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="88990-119">Given two instances of the <xref:System.IdentityModel.Claims.Claim> class, use the <xref:System.IdentityModel.Claims.Claim.Equals%2A> to make the comparison, as shown in the following code.</span></span>

     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]

### <a name="comparing-custom-claims-with-primitive-resource-types"></a><span data-ttu-id="88990-120">Сравнение пользовательских утверждений с типами-примитивами ресурсов</span><span class="sxs-lookup"><span data-stu-id="88990-120">Comparing custom claims with primitive resource types</span></span>

1. <span data-ttu-id="88990-121">Для пользовательских утверждений с типами-примитивами ресурсов сравнение может выполняться аналогично сравнению для встроенных утверждений, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="88990-121">For custom claims with primitive resource types, comparison can be performed as for built-in claims, as shown in the following code.</span></span>

     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]

2. <span data-ttu-id="88990-122">Для пользовательских утверждений с типами ресурсов на основе структур или классов тип ресурса должен переопределить метод <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="88990-122">For custom claims with structure or class based resource types, the resource type should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span>

3. <span data-ttu-id="88990-123">Сначала проверьте, имеет ли параметр `obj` значение `null`. Если да, верните значение `false`.</span><span class="sxs-lookup"><span data-stu-id="88990-123">First check whether the `obj` parameter is `null`, and if so, return `false`.</span></span>

     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]

4. <span data-ttu-id="88990-124">Затем вызовите метод <xref:System.Object.ReferenceEquals%2A> и передайте `this` и `obj` в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="88990-124">Next call <xref:System.Object.ReferenceEquals%2A> and pass `this` and `obj` as parameters.</span></span> <span data-ttu-id="88990-125">Если этот метод возвращает значение `true`, верните значение `true`.</span><span class="sxs-lookup"><span data-stu-id="88990-125">If it returns `true`, then return `true`.</span></span>

     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]

5. <span data-ttu-id="88990-126">Затем попытайтесь присвоить значение `obj` локальной переменной типа класса.</span><span class="sxs-lookup"><span data-stu-id="88990-126">Next attempt to assign `obj` to a local variable of the class type.</span></span> <span data-ttu-id="88990-127">Если эта попытка завершается неуспешно, ссылка имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="88990-127">If this fails, the reference is `null`.</span></span> <span data-ttu-id="88990-128">В этом случае верните значение `false`.</span><span class="sxs-lookup"><span data-stu-id="88990-128">In such cases, return `false`.</span></span>

6. <span data-ttu-id="88990-129">Выполните пользовательское сравнение, необходимое для правильного сравнения текущего утверждения с предоставленным утверждением.</span><span class="sxs-lookup"><span data-stu-id="88990-129">Perform the custom comparison necessary to correctly compare the current claim to the provided claim.</span></span>

## <a name="example"></a><span data-ttu-id="88990-130">Пример</span><span class="sxs-lookup"><span data-stu-id="88990-130">Example</span></span>

<span data-ttu-id="88990-131">В следующем примере показано сравнение пользовательских утверждений, где ресурсом утверждения является тип, отличный от типа-примитива.</span><span class="sxs-lookup"><span data-stu-id="88990-131">The following example shows a comparison of custom claims where the claim resource is a non-primitive type.</span></span>

[!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
[!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]

## <a name="see-also"></a><span data-ttu-id="88990-132">См. также</span><span class="sxs-lookup"><span data-stu-id="88990-132">See also</span></span>

- [<span data-ttu-id="88990-133">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="88990-133">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="88990-134">Практическое руководство. Создание настраиваемого утверждения</span><span class="sxs-lookup"><span data-stu-id="88990-134">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
