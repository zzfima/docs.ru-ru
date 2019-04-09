---
title: Отображение имен алгоритмов на криптографические классы
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 6ec98aabd92a7a0fed11482bdf6e5e8ddc045a7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098745"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="4c92d-102">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="4c92d-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="4c92d-103">Существует четыре способа создания криптографического объекта с помощью [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4c92d-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="4c92d-104">Создание объекта с помощью **новый** оператор.</span><span class="sxs-lookup"><span data-stu-id="4c92d-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="4c92d-105">Создайте объект, реализующий конкретный криптографический алгоритм, вызвав **создать** метод к абстрактному классу данного алгоритма.</span><span class="sxs-lookup"><span data-stu-id="4c92d-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="4c92d-106">Создайте объект, реализующий конкретный криптографический алгоритм, вызвав <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="4c92d-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="4c92d-107">Создание объекта, реализующего класс алгоритмов шифрования (например, симметричный блочный шифр) путем вызова **создать** метод на абстрактный класс для этого типа алгоритма (такие как <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="4c92d-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="4c92d-108">Например предположим, что разработчику нужно вычислить хэш SHA1 набора байтов.</span><span class="sxs-lookup"><span data-stu-id="4c92d-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="4c92d-109"><xref:System.Security.Cryptography> Пространство имен содержит две реализации алгоритма SHA1, одну реализацию полностью управляемыми и тот, который создает оболочку для CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="4c92d-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="4c92d-110">Разработчик может выбрать для создания экземпляра конкретной реализации SHA1 (такие как <xref:System.Security.Cryptography.SHA1Managed>) путем вызова **новый** оператор.</span><span class="sxs-lookup"><span data-stu-id="4c92d-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="4c92d-111">Тем не менее, если он не имеет значения, какой класс, среда CLR загружает до тех пор, пока этот класс реализует хэш-алгоритм SHA1, разработчик может создать объект путем вызова <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="4c92d-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4c92d-112">Этот метод вызывает метод **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, который должен возвращать реализацию алгоритма хэширования SHA1.</span><span class="sxs-lookup"><span data-stu-id="4c92d-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="4c92d-113">Разработчик также может вызвать **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** так, как по умолчанию конфигурации шифрования включает в себя короткие имена для алгоритмов, в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c92d-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="4c92d-114">Если это неважно, используется алгоритм хеширования, разработчик может вызвать <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> метод, который возвращает объект, реализующий интерфейс хэширования преобразования.</span><span class="sxs-lookup"><span data-stu-id="4c92d-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="4c92d-115">Отображение имен алгоритмов в файлах конфигурации</span><span class="sxs-lookup"><span data-stu-id="4c92d-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="4c92d-116">По умолчанию среда выполнения возвращает <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> объекта для всех четырех сценариев.</span><span class="sxs-lookup"><span data-stu-id="4c92d-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="4c92d-117">Тем не менее администратор компьютера можно изменить тип объекта, которое возвращают методы в последних двух сценариях.</span><span class="sxs-lookup"><span data-stu-id="4c92d-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="4c92d-118">Чтобы сделать это, необходимо сопоставить с понятным именем алгоритма к классу, который вы хотите использовать в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4c92d-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="4c92d-119">В следующем примере показано, как настроить среду выполнения, чтобы **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, и  **System.Security.Cryptography.HashAlgorithm.Create** возвращают `MySHA1HashClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="4c92d-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="4c92d-120">Можно указать имя атрибута в [< cryptoClass\> элемент](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (предыдущий пример имен атрибута `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="4c92d-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="4c92d-121">Значение атрибута в  **\<cryptoClass >** элемент представляет собой строку, среда CLR использует для поиска класса.</span><span class="sxs-lookup"><span data-stu-id="4c92d-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="4c92d-122">Можно использовать любую строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="4c92d-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="4c92d-123">Многие имена алгоритмов можно сопоставить с того же класса.</span><span class="sxs-lookup"><span data-stu-id="4c92d-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="4c92d-124">[ \<NameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) сопоставляет класс с одним понятным именем алгоритма.</span><span class="sxs-lookup"><span data-stu-id="4c92d-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="4c92d-125">**Имя** атрибут может быть либо строкой, которая используется при вызове **System.Security.Cryptography.CryptoConfig.CreateFromName** метода или имени класса абстрактный криптографии в <xref:System.Security.Cryptography> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="4c92d-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="4c92d-126">Значение **класс** атрибут — это имя атрибута в  **\<cryptoClass >** элемент.</span><span class="sxs-lookup"><span data-stu-id="4c92d-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c92d-127">Вы можете получить алгоритм SHA1, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> или **Security.CryptoConfig.CreateFromName("SHA1")** метод.</span><span class="sxs-lookup"><span data-stu-id="4c92d-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="4c92d-128">Каждый метод только гарантирует, что он возвращает объект, реализующий алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="4c92d-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="4c92d-129">Необходимо сопоставить каждый понятное имя алгоритма в тот же класс в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4c92d-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="4c92d-130">Список имен по умолчанию и классы, они сопоставляются, см. в разделе <xref:System.Security.Cryptography.CryptoConfig>.</span><span class="sxs-lookup"><span data-stu-id="4c92d-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c92d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4c92d-131">See also</span></span>

- [<span data-ttu-id="4c92d-132">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="4c92d-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="4c92d-133">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="4c92d-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
