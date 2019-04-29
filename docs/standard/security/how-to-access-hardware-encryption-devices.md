---
title: Практическое руководство. Доступ к устройствам аппаратного шифрования
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33af618ac3971df76683fd64346e1aa1e5977177
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795206"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="6cca6-102">Практическое руководство. Доступ к устройствам аппаратного шифрования</span><span class="sxs-lookup"><span data-stu-id="6cca6-102">How to: Access Hardware Encryption Devices</span></span>
<span data-ttu-id="6cca6-103">Класс <xref:System.Security.Cryptography.CspParameters> можно использовать для доступа к устройствам аппаратного шифрования.</span><span class="sxs-lookup"><span data-stu-id="6cca6-103">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="6cca6-104">Например, этот класс можно использовать для интеграции приложения со смарт-картой, аппаратным генератором случайных чисел или аппаратной реализацией определенного алгоритма шифрования.</span><span class="sxs-lookup"><span data-stu-id="6cca6-104">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  
  
 <span data-ttu-id="6cca6-105">Класс <xref:System.Security.Cryptography.CspParameters> создает поставщик служб шифрования (CSP), который обращается к правильно установленному устройству аппаратного шифрования.</span><span class="sxs-lookup"><span data-stu-id="6cca6-105">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="6cca6-106">Можно проверить доступность CSP, изучив следующий раздел реестра с помощью редактора реестра (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="6cca6-106">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="6cca6-107">Подпись данных при помощи карты с ключом</span><span class="sxs-lookup"><span data-stu-id="6cca6-107">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="6cca6-108">Создайте новый экземпляр класса <xref:System.Security.Cryptography.CspParameters>, передав в конструктор целочисленный тип поставщика и имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="6cca6-108">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="6cca6-109">Передайте соответствующие флаги в свойство <xref:System.Security.Cryptography.CspParameters.Flags%2A> созданного объекта <xref:System.Security.Cryptography.CspParameters>.</span><span class="sxs-lookup"><span data-stu-id="6cca6-109">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="6cca6-110">Например, передайте флаг <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>.</span><span class="sxs-lookup"><span data-stu-id="6cca6-110">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="6cca6-111">Создайте новый экземпляр класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>(например, класс <xref:System.Security.Cryptography.RSACryptoServiceProvider>), передав объект <xref:System.Security.Cryptography.CspParameters> в конструктор.</span><span class="sxs-lookup"><span data-stu-id="6cca6-111">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="6cca6-112">Подпишите данные при помощи одного из методов `Sign` и проверьте данные, используя один из методов `Verify`.</span><span class="sxs-lookup"><span data-stu-id="6cca6-112">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="6cca6-113">Формирование случайного числа при помощи аппаратного генератора случайных чисел</span><span class="sxs-lookup"><span data-stu-id="6cca6-113">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="6cca6-114">Создайте новый экземпляр класса <xref:System.Security.Cryptography.CspParameters>, передав в конструктор целочисленный тип поставщика и имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="6cca6-114">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="6cca6-115">Создайте новый экземпляр <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, передав объект <xref:System.Security.Cryptography.CspParameters> в конструктор.</span><span class="sxs-lookup"><span data-stu-id="6cca6-115">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="6cca6-116">Создайте случайное значение при помощи метода <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> или <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.</span><span class="sxs-lookup"><span data-stu-id="6cca6-116">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cca6-117">Пример</span><span class="sxs-lookup"><span data-stu-id="6cca6-117">Example</span></span>  
 <span data-ttu-id="6cca6-118">В примере кода ниже показано, как подписать данные при помощи смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="6cca6-118">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="6cca6-119">Этот пример кода создает объект <xref:System.Security.Cryptography.CspParameters>, который предоставляет смарт-карты, а затем инициализирует объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> при помощи CSP.</span><span class="sxs-lookup"><span data-stu-id="6cca6-119">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="6cca6-120">После этого примера подписывает и проверяет некоторые данные.</span><span class="sxs-lookup"><span data-stu-id="6cca6-120">The code example then signs and verifies some data.</span></span>  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6cca6-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6cca6-121">Compiling the Code</span></span>  
  
- <span data-ttu-id="6cca6-122">Включите пространства имен <xref:System> и <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="6cca6-122">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="6cca6-123">На компьютере должно быть установлено устройство чтения смарт-карт и соответствующие драйвера.</span><span class="sxs-lookup"><span data-stu-id="6cca6-123">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="6cca6-124">Необходимо инициализировать объект <xref:System.Security.Cryptography.CspParameters>, используя информацию, характерную для вашего устройства чтения смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="6cca6-124">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="6cca6-125">Дополнительные сведения см. в документации по устройству чтения смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="6cca6-125">For more information, see the documentation of your card reader.</span></span>
