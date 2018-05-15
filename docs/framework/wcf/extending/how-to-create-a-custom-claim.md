---
title: Практическое руководство. Создание пользовательского утверждения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 3ee707ae4e2a7dafeb7cb42d6d56eeece8f23306
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="2623c-102">Практическое руководство. Создание пользовательского утверждения</span><span class="sxs-lookup"><span data-stu-id="2623c-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="2623c-103">Инфраструктура модели удостоверения в Windows Communication Foundation (WCF) предоставляет набор встроенных типов утверждений и прав с вспомогательными функциями для создания <xref:System.IdentityModel.Claims.Claim> экземпляры с этими типами и правами.</span><span class="sxs-lookup"><span data-stu-id="2623c-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="2623c-104">Эти встроенные утверждения предназначены для моделирования информации, найденной в типах учетных данных клиента, которые WCF поддерживает по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2623c-104">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="2623c-105">Очень часто бывает достаточно встроенных утверждений; однако некоторые приложения требуют пользовательских утверждений.</span><span class="sxs-lookup"><span data-stu-id="2623c-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="2623c-106">Утверждение состоит из типа утверждения, ресурса, к которому применяется утверждение, и права, подтверждающегося через этот ресурс.</span><span class="sxs-lookup"><span data-stu-id="2623c-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="2623c-107">В этом разделе описывается создание пользовательского утверждения.</span><span class="sxs-lookup"><span data-stu-id="2623c-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="2623c-108">Создание пользовательского утверждения на основе примитивного типа данных</span><span class="sxs-lookup"><span data-stu-id="2623c-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1.  <span data-ttu-id="2623c-109">Создайте пользовательское утверждение, передав тип утверждения, значение ресурса и право конструктору <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="2623c-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="2623c-110">Выберите уникальное значение для типа утверждения.</span><span class="sxs-lookup"><span data-stu-id="2623c-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="2623c-111">Тип утверждения - это уникальный идентификатор строки.</span><span class="sxs-lookup"><span data-stu-id="2623c-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="2623c-112">На конструктор пользовательского утверждения возлагается обязанность убедиться в уникальности идентификатора строки, используемого для данного типа утверждения.</span><span class="sxs-lookup"><span data-stu-id="2623c-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="2623c-113">Список типов утверждений, которые определены в WCF см. в разделе <xref:System.IdentityModel.Claims.ClaimTypes> класса.</span><span class="sxs-lookup"><span data-stu-id="2623c-113">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="2623c-114">Выберите примитивный тип данных и значение для ресурса.</span><span class="sxs-lookup"><span data-stu-id="2623c-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="2623c-115">Ресурс - это объект.</span><span class="sxs-lookup"><span data-stu-id="2623c-115">A resource is an object.</span></span> <span data-ttu-id="2623c-116">Тип среды CLR ресурса может быть примитивом, например <xref:System.String> или <xref:System.Int32>, или любым сериализуемым типом.</span><span class="sxs-lookup"><span data-stu-id="2623c-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="2623c-117">Тип среды CLR ресурса должен быть сериализуемым, так как утверждения в различных точках сериализуются в WCF.</span><span class="sxs-lookup"><span data-stu-id="2623c-117">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="2623c-118">Примитивные типы являются сериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="2623c-118">Primitive types are serializable.</span></span>  
  
    3.  <span data-ttu-id="2623c-119">Выберите право, определяемое WCF или уникальное значение для пользовательского права.</span><span class="sxs-lookup"><span data-stu-id="2623c-119">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="2623c-120">Право - это уникальный идентификатор строки.</span><span class="sxs-lookup"><span data-stu-id="2623c-120">A right is a unique string identifier.</span></span> <span data-ttu-id="2623c-121">Права, которые определены в WCF определяются в <xref:System.IdentityModel.Claims.Rights> класса.</span><span class="sxs-lookup"><span data-stu-id="2623c-121">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="2623c-122">На конструктор пользовательского утверждения возлагается обязанность убедиться в уникальности идентификатора строки, используемого для данного права.</span><span class="sxs-lookup"><span data-stu-id="2623c-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="2623c-123">В следующем примере кода показано создание пользовательского утверждения с типом утверждения `http://example.org/claims/simplecustomclaim` для ресурса с именем `Driver's License` и правом <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="2623c-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="2623c-124">Создание пользовательского утверждения на основе непримитивного типа данных</span><span class="sxs-lookup"><span data-stu-id="2623c-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1.  <span data-ttu-id="2623c-125">Создайте пользовательское утверждение, передав тип утверждения, значение ресурса и право конструктору <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="2623c-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="2623c-126">Выберите уникальное значение для типа утверждения.</span><span class="sxs-lookup"><span data-stu-id="2623c-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="2623c-127">Тип утверждения - это уникальный идентификатор строки.</span><span class="sxs-lookup"><span data-stu-id="2623c-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="2623c-128">На конструктор пользовательского утверждения возлагается обязанность убедиться в уникальности идентификатора строки, используемого для данного типа утверждения.</span><span class="sxs-lookup"><span data-stu-id="2623c-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="2623c-129">Список типов утверждений, которые определены в WCF см. в разделе <xref:System.IdentityModel.Claims.ClaimTypes> класса.</span><span class="sxs-lookup"><span data-stu-id="2623c-129">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="2623c-130">Выберите или определите сериализуемый непримитивный тип для ресурса.</span><span class="sxs-lookup"><span data-stu-id="2623c-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="2623c-131">Ресурс - это объект.</span><span class="sxs-lookup"><span data-stu-id="2623c-131">A resource is an object.</span></span> <span data-ttu-id="2623c-132">Тип среды CLR ресурса должен быть сериализуемым, так как утверждения в различных точках сериализуются в WCF.</span><span class="sxs-lookup"><span data-stu-id="2623c-132">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="2623c-133">Примитивные типы уже являются сериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="2623c-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="2623c-134">При определении нового типа примените к классу атрибут <xref:System.Runtime.Serialization.DataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2623c-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="2623c-135">Также примените атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> ко всем членам нового типа, которые необходимо сериализовать как часть утверждения.</span><span class="sxs-lookup"><span data-stu-id="2623c-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="2623c-136">В следующем примере кода определяется пользовательский тип ресурса с именем `MyResourceType`.</span><span class="sxs-lookup"><span data-stu-id="2623c-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3.  <span data-ttu-id="2623c-137">Выберите право, определяемое WCF или уникальное значение для пользовательского права.</span><span class="sxs-lookup"><span data-stu-id="2623c-137">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="2623c-138">Право - это уникальный идентификатор строки.</span><span class="sxs-lookup"><span data-stu-id="2623c-138">A right is a unique string identifier.</span></span> <span data-ttu-id="2623c-139">Права, которые определены в WCF определяются в <xref:System.IdentityModel.Claims.Rights> класса.</span><span class="sxs-lookup"><span data-stu-id="2623c-139">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="2623c-140">На конструктор пользовательского утверждения возлагается обязанность убедиться в уникальности идентификатора строки, используемого для данного права.</span><span class="sxs-lookup"><span data-stu-id="2623c-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="2623c-141">В следующем примере кода показано создание пользовательского утверждения с типом утверждения `http://example.org/claims/complexcustomclaim`, пользовательским типом ресурса `MyResourceType` и правом <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="2623c-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="2623c-142">Пример</span><span class="sxs-lookup"><span data-stu-id="2623c-142">Example</span></span>  
 <span data-ttu-id="2623c-143">В следующем примере кода демонстрируется создание пользовательского утверждения с примитивным типом ресурса и пользовательского утверждения с непримитивным типом ресурса.</span><span class="sxs-lookup"><span data-stu-id="2623c-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="2623c-144">См. также</span><span class="sxs-lookup"><span data-stu-id="2623c-144">See Also</span></span>  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.Rights>  
 <xref:System.IdentityModel.Claims.ClaimTypes>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="2623c-145">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="2623c-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="2623c-146">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="2623c-146">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
