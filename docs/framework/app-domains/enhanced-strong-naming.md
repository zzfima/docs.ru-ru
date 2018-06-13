---
title: Усовершенствованное строгое именование
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf4a8df87cd507f2bfb17086e83dc8374a22fe71
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746895"
---
# <a name="enhanced-strong-naming"></a><span data-ttu-id="f6972-102">Усовершенствованное строгое именование</span><span class="sxs-lookup"><span data-stu-id="f6972-102">Enhanced Strong Naming</span></span>
<span data-ttu-id="f6972-103">Подпись строгого имени — это механизм идентификации сборок в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6972-103">A strong name signature is an identity mechanism in the .NET Framework for identifying assemblies.</span></span> <span data-ttu-id="f6972-104">Это цифровая подпись с открытым ключом, которая обычно используется для проверки целостности данных, передаваемых от инициатора (подписывающего) к получателю (проверяющему).</span><span class="sxs-lookup"><span data-stu-id="f6972-104">It is a public-key digital signature that is typically used to verify the integrity of data being passed from an originator (signer) to a recipient (verifier).</span></span> <span data-ttu-id="f6972-105">Эта подпись используется в виде уникального идентификатора сборки и гарантирует, что ссылки на сборку не являются неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="f6972-105">This signature is used as a unique identity for an assembly and ensures that references to the assembly are not ambiguous.</span></span> <span data-ttu-id="f6972-106">Подписывание сборки является частью процесса сборки, что затем проверяется при ее загрузке.</span><span class="sxs-lookup"><span data-stu-id="f6972-106">The assembly is signed as part of the build process and then verified when it is loaded.</span></span>  
  
 <span data-ttu-id="f6972-107">Подписи строгого имени помогают предотвратить подделку сборки на стороне злоумышленника с последующей повторной подписью сборки оригинальным ключом подписавшего.</span><span class="sxs-lookup"><span data-stu-id="f6972-107">Strong name signatures help prevent malicious parties from tampering with an assembly and then re-signing the assembly with the original signer’s key.</span></span> <span data-ttu-id="f6972-108">Но ключи строгого имени не содержат никаких сведений об издателе, а также не содержат иерархию сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f6972-108">However, strong name keys don’t contain any reliable information about the publisher, nor do they contain a certificate hierarchy.</span></span> <span data-ttu-id="f6972-109">Подпись строгого имени не гарантирует, что подписавшему сборку человеку можно доверять, и не указывает на то, что человек является правомерным владельцем ключа; она означает только то, что владелец ключа подписал сборку.</span><span class="sxs-lookup"><span data-stu-id="f6972-109">A strong name signature does not guarantee the trustworthiness of the person who signed the assembly or indicate whether that person was a legitimate owner of the key; it indicates only that the owner of the key signed the assembly.</span></span> <span data-ttu-id="f6972-110">Поэтому не рекомендуется использовать подпись строгого имени как средство проверки безопасности на доверие к коду сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="f6972-110">Therefore, we do not recommend using a strong name signature as a security validator for trusting third-party code.</span></span> <span data-ttu-id="f6972-111">Рекомендуемым способом проверки подлинности кода является Microsoft Authenticode.</span><span class="sxs-lookup"><span data-stu-id="f6972-111">Microsoft Authenticode is the recommended way to authenticate code.</span></span>  
  
## <a name="limitations-of-conventional-strong-names"></a><span data-ttu-id="f6972-112">Ограничения обычных строгих имен</span><span class="sxs-lookup"><span data-stu-id="f6972-112">Limitations of Conventional Strong Names</span></span>  
 <span data-ttu-id="f6972-113">Технология строгого именования, используемая в версиях до [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], имеет указанные ниже недостатки.</span><span class="sxs-lookup"><span data-stu-id="f6972-113">The strong naming technology used in versions before the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] has the following shortcomings:</span></span>  
  
-   <span data-ttu-id="f6972-114">Ключи постоянно подвержены атакам, а улучшенные методы и оборудование облегчают поиск закрытого ключа по открытому.</span><span class="sxs-lookup"><span data-stu-id="f6972-114">Keys are constantly under attack, and improved techniques and hardware make it easier to infer a private key from a public key.</span></span> <span data-ttu-id="f6972-115">Для защиты от атак необходимы более длинные ключи.</span><span class="sxs-lookup"><span data-stu-id="f6972-115">To guard against attacks, larger keys are necessary.</span></span> <span data-ttu-id="f6972-116">Версии .NET Framework до [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предоставляют возможность подписывания с помощью ключа любого размера (размер по умолчанию — 1024 бита), но подпись сборки новым ключом испортит все двоичные файлы, ссылающиеся на старый идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="f6972-116">.NET Framework versions before the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] provide the ability to sign with any size key (the default size is 1024 bits), but signing an assembly with a new key breaks all binaries that reference the older identity of the assembly.</span></span> <span data-ttu-id="f6972-117">Поэтому изменение размера ключа подписи является крайне сложным, если необходимо обеспечить совместимость.</span><span class="sxs-lookup"><span data-stu-id="f6972-117">Therefore, it is extremely difficult to upgrade the size of a signing key if you want to maintain compatibility.</span></span>  
  
-   <span data-ttu-id="f6972-118">Подпись строгого имени поддерживает только алгоритм SHA-1.</span><span class="sxs-lookup"><span data-stu-id="f6972-118">Strong name signing supports only the SHA-1 algorithm.</span></span> <span data-ttu-id="f6972-119">Недавно было показано, что алгоритма SHA-1 недостаточно для обеспечения безопасности хэширования.</span><span class="sxs-lookup"><span data-stu-id="f6972-119">SHA-1 has recently been found to be inadequate for secure hashing applications.</span></span> <span data-ttu-id="f6972-120">Поэтому необходим более надежный алгоритм (SHA-256 или выше).</span><span class="sxs-lookup"><span data-stu-id="f6972-120">Therefore, a stronger algorithm (SHA-256 or greater) is necessary.</span></span> <span data-ttu-id="f6972-121">Возможно, алгоритм SHA-1 утратит статус совместимого с FIPS, что станет проблемой для тех, кто предпочитает использовать только FIPS-совместимое программное обеспечение и алгоритмы.</span><span class="sxs-lookup"><span data-stu-id="f6972-121">It is possible that SHA-1 will lose its FIPS-compliant standing, which would present problems for those who choose to use only FIPS-compliant software and algorithms.</span></span>  
  
## <a name="advantages-of-enhanced-strong-names"></a><span data-ttu-id="f6972-122">Преимущества улучшенных строгих имен</span><span class="sxs-lookup"><span data-stu-id="f6972-122">Advantages of Enhanced Strong Names</span></span>  
 <span data-ttu-id="f6972-123">Основными преимуществами улучшенных строгих имен являются совместимость с уже существующими строгими именами и возможность утверждения эквивалентности одного идентификатора другому.</span><span class="sxs-lookup"><span data-stu-id="f6972-123">The main advantages of enhanced strong names are compatibility with pre-existing strong names and the ability to claim that one identity is equivalent to another:</span></span>  
  
-   <span data-ttu-id="f6972-124">Разработчики, которые имеют уже существующие подписанные сборки, могут перенести формирование их идентификаторов на алгоритм SHA-2, сохранив при этом совместимость со сборками, которые ссылаются на старые идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="f6972-124">Developers who have pre-existing signed assemblies can migrate their identities to the SHA-2 algorithms while maintaining compatibility with assemblies that reference the old identities.</span></span>  
  
-   <span data-ttu-id="f6972-125">Разработчики, которые создают новые сборки и не имеют существующих подписей строгого имени, могут использовать более безопасные алгоритмы SHA-2 и подписывать сборки так, как они делали всегда.</span><span class="sxs-lookup"><span data-stu-id="f6972-125">Developers who create new assemblies and are not concerned with pre-existing strong name signatures can use the more secure SHA-2 algorithms and sign the assemblies as they always have.</span></span>  
  
## <a name="using-enhanced-strong-names"></a><span data-ttu-id="f6972-126">Использование улучшенных строгих имен</span><span class="sxs-lookup"><span data-stu-id="f6972-126">Using Enhanced Strong Names</span></span>  
 <span data-ttu-id="f6972-127">Ключи строгого имени состоят из ключа подписи и ключа удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-127">Strong name keys consist of a signature key and an identity key.</span></span> <span data-ttu-id="f6972-128">Сборка подписывается с помощью ключа подписи и не зависит от ключа удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-128">The assembly is signed with the signature key and is identified by the identity key.</span></span> <span data-ttu-id="f6972-129">До выхода версии [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] эти ключи были идентичными.</span><span class="sxs-lookup"><span data-stu-id="f6972-129">Prior to the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], these two keys were identical.</span></span> <span data-ttu-id="f6972-130">Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ключ удостоверения остается таким же, как и в более ранних версиях платформы .NET Framework, а ключ подписи улучшается с использованием более надежного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="f6972-130">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the identity key remains the same as in earlier .NET Framework versions, but the signature key is enhanced with a stronger hash algorithm.</span></span> <span data-ttu-id="f6972-131">Кроме того, ключ подписи подписывается ключом удостоверения для создания подписи другой стороны.</span><span class="sxs-lookup"><span data-stu-id="f6972-131">In addition, the signature key is signed with the identity key to create a counter-signature.</span></span>  
  
 <span data-ttu-id="f6972-132">Атрибут <xref:System.Reflection.AssemblySignatureKeyAttribute> позволяет метаданным сборки использовать уже существующий открытый ключ для идентификации сборки, что позволяет старым ссылкам на сборки продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="f6972-132">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute enables the assembly metadata to use the pre-existing public key for assembly identity, which allows old assembly references to continue to work.</span></span>  <span data-ttu-id="f6972-133">Атрибут <xref:System.Reflection.AssemblySignatureKeyAttribute> использует подпись другой стороны для проверки того, является ли владелец нового ключа подписи также владельцем старого ключа удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-133">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute uses the counter-signature to ensure that the owner of the new signature key is also the owner of the old identity key.</span></span>  
  
### <a name="signing-with-sha-2-without-key-migration"></a><span data-ttu-id="f6972-134">Подписывание с использованием SHA-2 без переноса ключа</span><span class="sxs-lookup"><span data-stu-id="f6972-134">Signing with SHA-2, Without Key Migration</span></span>  
 <span data-ttu-id="f6972-135">Чтобы подписать сборку без переноса подписи строгого имени, выполните указанные ниже команды в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="f6972-135">Run the following commands from a Command Prompt window to sign an assembly without migrating a strong name signature:</span></span>  
  
1.  <span data-ttu-id="f6972-136">Создайте ключ удостоверения (если необходимо).</span><span class="sxs-lookup"><span data-stu-id="f6972-136">Generate the new identity key (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  <span data-ttu-id="f6972-137">Извлеките открытый ключ удостоверения и укажите, что при подписывании этим ключом необходимо использовать алгоритм SHA-2.</span><span class="sxs-lookup"><span data-stu-id="f6972-137">Extract the identity public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  <span data-ttu-id="f6972-138">Используйте отложенную подпись сборки с помощью файла с открытым ключом удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-138">Delay-sign the assembly with the identity public key file.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  <span data-ttu-id="f6972-139">Повторно подпишите сборку с помощью полной пары ключей удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-139">Re-sign the assembly with the full identity key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a><span data-ttu-id="f6972-140">Подписывание с использованием SHA-2 с переносом ключа</span><span class="sxs-lookup"><span data-stu-id="f6972-140">Signing with SHA-2, with Key Migration</span></span>  
 <span data-ttu-id="f6972-141">Чтобы подписать сборку с переносом подписи строгого имени, выполните указанные ниже команды в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="f6972-141">Run the following commands from a Command Prompt window to sign an assembly with a migrated strong name signature.</span></span>  
  
1.  <span data-ttu-id="f6972-142">Создайте пару ключей удостоверения и подписи (если необходимо).</span><span class="sxs-lookup"><span data-stu-id="f6972-142">Generate an identity and signature key pair (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  <span data-ttu-id="f6972-143">Извлеките открытый ключ подписи и укажите, что при подписывании этим ключом необходимо использовать алгоритм SHA-2.</span><span class="sxs-lookup"><span data-stu-id="f6972-143">Extract the signature public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  <span data-ttu-id="f6972-144">Извлеките открытый ключ удостоверения, определяющий хэш-алгоритм, с помощью которого создается подпись другой стороны.</span><span class="sxs-lookup"><span data-stu-id="f6972-144">Extract the identity public key, which determines the hash algorithm that generates a counter-signature.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  <span data-ttu-id="f6972-145">Создайте параметры для атрибута <xref:System.Reflection.AssemblySignatureKeyAttribute> и прикрепите атрибут к сборке.</span><span class="sxs-lookup"><span data-stu-id="f6972-145">Generate the parameters for a <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute, and attach the attribute to the assembly.</span></span>  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  <span data-ttu-id="f6972-146">Используйте отложенную подпись сборки с помощью открытого ключа удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-146">Delay-sign the assembly with the identity public key.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6.  <span data-ttu-id="f6972-147">Подпишите сборку с помощью полной пары ключей удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f6972-147">Fully sign the assembly with the signature key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f6972-148">См. также</span><span class="sxs-lookup"><span data-stu-id="f6972-148">See Also</span></span>  
 [<span data-ttu-id="f6972-149">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="f6972-149">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
