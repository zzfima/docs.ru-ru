---
title: Настройка криптографических классов
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 23bf831a4374add55258f5fb41c17a5d4a8f14c3
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832816"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="a5c51-102">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="a5c51-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="a5c51-103">Windows Software Development Kit (SDK) позволяет администраторам компьютера настраивать алгоритмы шифрования по умолчанию и реализаций алгоритмов, в .NET Framework и соответствующих приложениях.</span><span class="sxs-lookup"><span data-stu-id="a5c51-103">The Windows Software Development Kit (SDK) allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="a5c51-104">К примеру в организации имеет собственную реализацию алгоритма шифрования можно использовать эту реализацию, поставляемых по умолчанию вместо реализации в пакете SDK для Windows.</span><span class="sxs-lookup"><span data-stu-id="a5c51-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="a5c51-105">Несмотря на то, что управляемые приложения, использующие шифрование всегда можно явно привязать к конкретной реализации, рекомендуется, чтобы они создавали криптографические объекты с помощью системы настройки шифрования.</span><span class="sxs-lookup"><span data-stu-id="a5c51-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5c51-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a5c51-106">In This Section</span></span>  
 [<span data-ttu-id="a5c51-107">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="a5c51-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="a5c51-108">Описывает способ сопоставления имени алгоритма с криптографическим классом.</span><span class="sxs-lookup"><span data-stu-id="a5c51-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="a5c51-109">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="a5c51-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="a5c51-110">Описывает способ сопоставления идентификатора объекта в криптографическому алгоритму.</span><span class="sxs-lookup"><span data-stu-id="a5c51-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a5c51-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a5c51-111">Related Sections</span></span>  
 [<span data-ttu-id="a5c51-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a5c51-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="a5c51-113">Обзор службы шифрования, предоставляемые пакетом SDK для Windows.</span><span class="sxs-lookup"><span data-stu-id="a5c51-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="a5c51-114">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="a5c51-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="a5c51-115">Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="a5c51-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
