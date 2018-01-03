---
title: "Отображение имен алгоритмов на криптографические классы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9c9c5b1f69200d4ee5d39c98445b668813718dd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="52678-102">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="52678-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="52678-103">Существует четыре способа создания криптографического объекта с помощью [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="52678-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="52678-104">Создание объекта с помощью **новый** оператор.</span><span class="sxs-lookup"><span data-stu-id="52678-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="52678-105">Создание объекта, реализующего конкретный криптографический алгоритм с помощью метода **создать** метод к абстрактному классу данного алгоритма.</span><span class="sxs-lookup"><span data-stu-id="52678-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="52678-106">Создание объекта, реализующего конкретный криптографический алгоритм с помощью метода <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="52678-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="52678-107">Создание объекта, реализующего класс алгоритмов шифрования (например, симметричный блочный шифр) с помощью метода **создать** метод абстрактного класса для этого типа алгоритма (например, <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="52678-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="52678-108">Например предположим, что разработчику нужно вычислить хэш SHA1 набора байтов.</span><span class="sxs-lookup"><span data-stu-id="52678-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="52678-109"><xref:System.Security.Cryptography> Пространство имен содержит две реализации алгоритма SHA1, одна реализация полностью управляемые и один, который упаковывает CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="52678-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="52678-110">Разработчик может использовать для создания экземпляра конкретной реализации SHA1 (такие как <xref:System.Security.Cryptography.SHA1Managed>) путем вызова **новый** оператор.</span><span class="sxs-lookup"><span data-stu-id="52678-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="52678-111">Тем не менее, если он не имеет значения, какой класс общеязыковая среда выполнения загружает при условии, что класс реализует хэш-алгоритмом SHA1, разработчик может создать объект путем вызова <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="52678-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="52678-112">Этот метод вызывает метод **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, который должен вернуть реализацию хэш-алгоритмом SHA1.</span><span class="sxs-lookup"><span data-stu-id="52678-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="52678-113">Разработчик также может вызывать **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** так, как по умолчанию конфигурации шифрования включает в себя короткие имена для алгоритмов, поставляется в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52678-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="52678-114">Если он не имеет значения, используется алгоритм хеширования, разработчик может вызывать <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> метод, который возвращает объект, реализующий интерфейс хэширования преобразования.</span><span class="sxs-lookup"><span data-stu-id="52678-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="52678-115">Сопоставление имен алгоритмов в файлах конфигурации</span><span class="sxs-lookup"><span data-stu-id="52678-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="52678-116">По умолчанию среда выполнения возвращает <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> объекта для всех четырех сценариев.</span><span class="sxs-lookup"><span data-stu-id="52678-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="52678-117">Тем не менее администратор компьютера может изменить тип объекта, возвращаемые методами в двух последних случаях.</span><span class="sxs-lookup"><span data-stu-id="52678-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="52678-118">Чтобы сделать это, необходимо сопоставить с понятным именем алгоритма класса, который будет использоваться в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="52678-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="52678-119">В следующем примере показано, как настройки среды выполнения, чтобы **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, и  **System.Security.Cryptography.HashAlgorithm.Create** возвращают `MySHA1HashClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="52678-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="52678-120">Можно указать имя атрибута в [< cryptoClass\> элемент](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (предыдущий пример имена атрибут `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="52678-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="52678-121">Значение атрибута в  **\<cryptoClass >** элемент представляет собой строку, общеязыковая среда выполнения использует для поиска класса.</span><span class="sxs-lookup"><span data-stu-id="52678-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="52678-122">Можно использовать любую строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="52678-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="52678-123">Много имен алгоритмов можно сопоставить с того же класса.</span><span class="sxs-lookup"><span data-stu-id="52678-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="52678-124">[ \<NameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) сопоставляет класс с одним понятным именем алгоритма.</span><span class="sxs-lookup"><span data-stu-id="52678-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="52678-125">**Имя** атрибута может быть либо строка, используемая при вызове **System.Security.Cryptography.CryptoConfig.CreateFromName** метода или имени класса абстрактный шифрования в <xref:System.Security.Cryptography> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="52678-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="52678-126">Значение **класса** атрибут — это имя атрибута в  **\<cryptoClass >** элемента.</span><span class="sxs-lookup"><span data-stu-id="52678-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52678-127">Алгоритм SHA1 можно получить, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> или **Security.CryptoConfig.CreateFromName("SHA1")** метод.</span><span class="sxs-lookup"><span data-stu-id="52678-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="52678-128">Каждый метод гарантирует только то, что он возвращает объект, реализующий алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="52678-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="52678-129">Необходимо сопоставить каждое понятное имя алгоритма в тот же класс в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="52678-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="52678-130">Список имен по умолчанию и классы, они сопоставляются. в разделе <xref:System.Security.Cryptography.CryptoConfig>.</span><span class="sxs-lookup"><span data-stu-id="52678-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52678-131">См. также</span><span class="sxs-lookup"><span data-stu-id="52678-131">See Also</span></span>  
 [<span data-ttu-id="52678-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="52678-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="52678-133">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="52678-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
