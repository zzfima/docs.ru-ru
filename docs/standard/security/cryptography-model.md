---
title: Модель криптографии .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET Framework], model
- encryption [.NET Framework], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: f0c00e4cc866c537fe26dd1ad466d6cde95bc608
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706231"
---
# <a name="net-framework-cryptography-model"></a><span data-ttu-id="38902-102">Модель криптографии .NET Framework</span><span class="sxs-lookup"><span data-stu-id="38902-102">.NET Framework Cryptography Model</span></span>

<span data-ttu-id="38902-103">Платформа .NET Framework предоставляет реализации многих стандартных алгоритмов шифрования.</span><span class="sxs-lookup"><span data-stu-id="38902-103">The .NET Framework provides implementations of many standard cryptographic algorithms.</span></span> <span data-ttu-id="38902-104">Эти алгоритмы просты в использовании и имеют максимально безопасные свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38902-104">These algorithms are easy to use and have the safest possible default properties.</span></span> <span data-ttu-id="38902-105">Кроме того, криптографическая модель наследования объектов, поточно-ориентированная структура и конфигурация платформы .NET Framework являются чрезвычайно расширяемыми.</span><span class="sxs-lookup"><span data-stu-id="38902-105">In addition, the .NET Framework cryptography model of object inheritance, stream design, and configuration is extremely extensible.</span></span>

## <a name="object-inheritance"></a><span data-ttu-id="38902-106">Наследование объектов</span><span class="sxs-lookup"><span data-stu-id="38902-106">Object Inheritance</span></span>

<span data-ttu-id="38902-107">Система безопасности .NET Framework реализует расширяемую модель наследования производных классов.</span><span class="sxs-lookup"><span data-stu-id="38902-107">The .NET Framework security system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="38902-108">Иерархия имеет представленный ниже вид.</span><span class="sxs-lookup"><span data-stu-id="38902-108">The hierarchy is as follows:</span></span>

- <span data-ttu-id="38902-109">Класс типа алгоритма, например <xref:System.Security.Cryptography.SymmetricAlgorithm>, <xref:System.Security.Cryptography.AsymmetricAlgorithm> или <xref:System.Security.Cryptography.HashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="38902-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="38902-110">Этот уровень является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="38902-110">This level is abstract.</span></span>

- <span data-ttu-id="38902-111">Класс алгоритма, наследующий от класса типа алгоритма, например <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2> или <xref:System.Security.Cryptography.ECDiffieHellman>.</span><span class="sxs-lookup"><span data-stu-id="38902-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="38902-112">Этот уровень является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="38902-112">This level is abstract.</span></span>

- <span data-ttu-id="38902-113">Реализация класса алгоритма, наследующего от класса алгоритма, например <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> или <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="38902-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="38902-114">Этот уровень полностью реализован.</span><span class="sxs-lookup"><span data-stu-id="38902-114">This level is fully implemented.</span></span>

<span data-ttu-id="38902-115">При помощи этой системы производных классов можно легко добавить новый алгоритм или новую реализацию существующего алгоритма.</span><span class="sxs-lookup"><span data-stu-id="38902-115">Using this pattern of derived classes, it is easy to add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="38902-116">Например, чтобы создать новый алгоритм открытого ключа, можно наследовать от класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="38902-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="38902-117">Чтобы создать новую реализацию определенного алгоритма, можно создать неабстрактный производный класс этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="38902-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>

## <a name="how-algorithms-are-implemented-in-the-net-framework"></a><span data-ttu-id="38902-118">Реализация алгоритмов в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="38902-118">How Algorithms Are Implemented in the .NET Framework</span></span>

<span data-ttu-id="38902-119">В качестве примера различных реализаций, доступных для алгоритма, рассмотрим симметричные алгоритмы.</span><span class="sxs-lookup"><span data-stu-id="38902-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="38902-120">Основой для всех симметричных алгоритмов является <xref:System.Security.Cryptography.SymmetricAlgorithm>, который наследуется следующими алгоритмами:</span><span class="sxs-lookup"><span data-stu-id="38902-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by the following algorithms:</span></span>

1. <xref:System.Security.Cryptography.Aes>

2. <xref:System.Security.Cryptography.DES>

3. <xref:System.Security.Cryptography.RC2>

4. <xref:System.Security.Cryptography.Rijndael>

5. <xref:System.Security.Cryptography.TripleDES>

<span data-ttu-id="38902-121"><xref:System.Security.Cryptography.Aes> наследуется двумя классами: <xref:System.Security.Cryptography.AesCryptoServiceProvider> и <xref:System.Security.Cryptography.AesManaged>.</span><span class="sxs-lookup"><span data-stu-id="38902-121"><xref:System.Security.Cryptography.Aes> is inherited by two classes: <xref:System.Security.Cryptography.AesCryptoServiceProvider> and <xref:System.Security.Cryptography.AesManaged>.</span></span> <span data-ttu-id="38902-122">Класс <xref:System.Security.Cryptography.AesCryptoServiceProvider> является оболочкой реализации CAPI (Windows Cryptography API) для AES, тогда как класс <xref:System.Security.Cryptography.AesManaged> написан полностью в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="38902-122">The <xref:System.Security.Cryptography.AesCryptoServiceProvider> class is a wrapper around the Windows Cryptography API (CAPI) implementation of Aes, whereas the <xref:System.Security.Cryptography.AesManaged> class is written entirely in managed code.</span></span> <span data-ttu-id="38902-123">Имеется также и третий тип реализации — CNG (Cryptography Next Generation), который дополняет реализацию в управляемом коде и реализацию CAPI.</span><span class="sxs-lookup"><span data-stu-id="38902-123">There is also a third type of implementation, Cryptography Next Generation (CNG), in addition to the managed and CAPI implementations.</span></span> <span data-ttu-id="38902-124">Примером алгоритма CNG является <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="38902-124">An example of a CNG algorithm is <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="38902-125">Алгоритмы CNG доступны в Windows Vista и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="38902-125">CNG algorithms are available on Windows Vista and later.</span></span>

<span data-ttu-id="38902-126">Можно выбрать ту реализацию, которая подходит вам лучше всего.</span><span class="sxs-lookup"><span data-stu-id="38902-126">You can choose which implementation is best for you.</span></span>  <span data-ttu-id="38902-127">Реализации в управляемом коде доступны на всех платформах, поддерживающих .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38902-127">The managed implementations are available on all platforms that support the .NET Framework.</span></span>  <span data-ttu-id="38902-128">Реализации CAPI доступны в старых операционных системах и больше не разрабатываются.</span><span class="sxs-lookup"><span data-stu-id="38902-128">The CAPI implementations are available on older operating systems, and are no longer being developed.</span></span> <span data-ttu-id="38902-129">CNG — это самая последняя реализация, при помощи которой будет вестись разработка новых приложений.</span><span class="sxs-lookup"><span data-stu-id="38902-129">CNG is the very latest implementation where new development will take place.</span></span> <span data-ttu-id="38902-130">Однако реализации в управляемом коде не сертифицированы по федеральным стандартам на обработку информации (FIPS) и могут работать медленнее, чем классы-оболочки.</span><span class="sxs-lookup"><span data-stu-id="38902-130">However, the managed implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the wrapper classes.</span></span>

## <a name="stream-design"></a><span data-ttu-id="38902-131">Поточно-ориентированный подход</span><span class="sxs-lookup"><span data-stu-id="38902-131">Stream Design</span></span>

<span data-ttu-id="38902-132">Среда CLR использует поточно-ориентированный подход для реализации симметричных алгоритмов и алгоритмов хэширования.</span><span class="sxs-lookup"><span data-stu-id="38902-132">The common language runtime uses a stream-oriented design for implementing symmetric algorithms and hash algorithms.</span></span> <span data-ttu-id="38902-133">Основа такого подхода — класс <xref:System.Security.Cryptography.CryptoStream>, производный от класса <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="38902-133">The core of this design is the <xref:System.Security.Cryptography.CryptoStream> class, which derives from the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="38902-134">Основанные на потоках криптографические объекты поддерживают единый стандартный интерфейс (`CryptoStream`) для обработки той части объекта, которая отвечает за передачу данных.</span><span class="sxs-lookup"><span data-stu-id="38902-134">Stream-based cryptographic objects support a single standard interface (`CryptoStream`) for handling the data transfer portion of the object.</span></span> <span data-ttu-id="38902-135">Поскольку все объекты построены на базе стандартного интерфейса, можно связывать друг с другом несколько объектов (таких как хэш-объект и объект шифрования), а также выполнять несколько операций с данными без использования промежуточного хранилища.</span><span class="sxs-lookup"><span data-stu-id="38902-135">Because all the objects are built on a standard interface, you can chain together multiple objects (such as a hash object followed by an encryption object), and you can perform multiple operations on the data without needing any intermediate storage for it.</span></span> <span data-ttu-id="38902-136">Потоковая модель также позволяет создавать объекты из объектов меньшего размера.</span><span class="sxs-lookup"><span data-stu-id="38902-136">The streaming model also enables you to build objects from smaller objects.</span></span> <span data-ttu-id="38902-137">Например, объединенный алгоритм шифрования и хэширования можно просмотреть как единый объект потока, хотя этот объект может состоять из набора объектов потока.</span><span class="sxs-lookup"><span data-stu-id="38902-137">For example, a combined encryption and hash algorithm can be viewed as a single stream object, although this object might be built from a set of stream objects.</span></span>

## <a name="cryptographic-configuration"></a><span data-ttu-id="38902-138">Криптографическая конфигурация</span><span class="sxs-lookup"><span data-stu-id="38902-138">Cryptographic Configuration</span></span>

<span data-ttu-id="38902-139">Криптографическая конфигурация позволяет разрешить определенную реализацию алгоритма до имени алгоритма, что обеспечивает расширяемость криптографических классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38902-139">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET Framework cryptography classes.</span></span> <span data-ttu-id="38902-140">Вы можете добавить свою собственную аппаратную или программную реализацию алгоритма и сопоставить ее с необходимым именем алгоритма.</span><span class="sxs-lookup"><span data-stu-id="38902-140">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="38902-141">Если алгоритм не задан в файле конфигурации, используются параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38902-141">If an algorithm is not specified in the configuration file, the default settings are used.</span></span> <span data-ttu-id="38902-142">Дополнительные сведения о конфигурации криптографии см. в разделе [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span><span class="sxs-lookup"><span data-stu-id="38902-142">For more information about cryptographic configuration, see [Configuring Cryptography Classes](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span></span>

## <a name="choosing-an-algorithm"></a><span data-ttu-id="38902-143">Выбор алгоритма</span><span class="sxs-lookup"><span data-stu-id="38902-143">Choosing an Algorithm</span></span>

<span data-ttu-id="38902-144">Алгоритм можно выбирать, исходя из различных причин, например для обеспечения целостности данных, для обеспечения конфиденциальности данных или для создания ключа.</span><span class="sxs-lookup"><span data-stu-id="38902-144">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="38902-145">Симметричные и хэш-алгоритмы предназначены для защиты данных от нарушения целостности (защита от изменения) или конфиденциальности (защита от просмотра).</span><span class="sxs-lookup"><span data-stu-id="38902-145">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="38902-146">Хэш-алгоритмы используются в основном для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="38902-146">Hash algorithms are used primarily for data integrity.</span></span>

<span data-ttu-id="38902-147">Ниже приведен список рекомендуемых алгоритмов в зависимости от приложения.</span><span class="sxs-lookup"><span data-stu-id="38902-147">Here is a list of recommended algorithms by application:</span></span>

- <span data-ttu-id="38902-148">Конфиденциальность данных:</span><span class="sxs-lookup"><span data-stu-id="38902-148">Data privacy:</span></span>

  - <xref:System.Security.Cryptography.Aes>

- <span data-ttu-id="38902-149">Целостность данных:</span><span class="sxs-lookup"><span data-stu-id="38902-149">Data integrity:</span></span>

  - <xref:System.Security.Cryptography.HMACSHA256>

  - <xref:System.Security.Cryptography.HMACSHA512>

- <span data-ttu-id="38902-150">Цифровая подпись.</span><span class="sxs-lookup"><span data-stu-id="38902-150">Digital signature:</span></span>

  - <xref:System.Security.Cryptography.ECDsa>

  - <xref:System.Security.Cryptography.RSA>

- <span data-ttu-id="38902-151">Обмен ключами:</span><span class="sxs-lookup"><span data-stu-id="38902-151">Key exchange:</span></span>

  - <xref:System.Security.Cryptography.ECDiffieHellman>

  - <xref:System.Security.Cryptography.RSA>

- <span data-ttu-id="38902-152">Генерация случайных чисел:</span><span class="sxs-lookup"><span data-stu-id="38902-152">Random number generation:</span></span>

  - <xref:System.Security.Cryptography.RNGCryptoServiceProvider>

- <span data-ttu-id="38902-153">Формирование ключа из пароля:</span><span class="sxs-lookup"><span data-stu-id="38902-153">Generating a key from a password:</span></span>

  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a><span data-ttu-id="38902-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="38902-154">See also</span></span>

- [<span data-ttu-id="38902-155">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="38902-155">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
