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
ms.openlocfilehash: b5c1178519601d7dcb7c5b3014f413b6436746fb
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816172"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="5f906-102">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="5f906-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="5f906-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Позволяет администраторам компьютера настраивать алгоритмы шифрования по умолчанию и реализаций алгоритмов, в .NET Framework и соответствующих приложениях.</span><span class="sxs-lookup"><span data-stu-id="5f906-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="5f906-104">К примеру в организации имеет собственную реализацию алгоритма шифрования можно использовать эту реализацию, поставляемых по умолчанию вместо реализации в пакете SDK для Windows.</span><span class="sxs-lookup"><span data-stu-id="5f906-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="5f906-105">Несмотря на то, что управляемые приложения, использующие шифрование всегда можно явно привязать к конкретной реализации, рекомендуется, чтобы они создавали криптографические объекты с помощью системы настройки шифрования.</span><span class="sxs-lookup"><span data-stu-id="5f906-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f906-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5f906-106">In This Section</span></span>  
 [<span data-ttu-id="5f906-107">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="5f906-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="5f906-108">Описывает способ сопоставления имени алгоритма с криптографическим классом.</span><span class="sxs-lookup"><span data-stu-id="5f906-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="5f906-109">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="5f906-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="5f906-110">Описывает способ сопоставления идентификатора объекта в криптографическому алгоритму.</span><span class="sxs-lookup"><span data-stu-id="5f906-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f906-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5f906-111">Related Sections</span></span>  
 [<span data-ttu-id="5f906-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5f906-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="5f906-113">Обзор службы шифрования, предоставляемые пакетом SDK для Windows.</span><span class="sxs-lookup"><span data-stu-id="5f906-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="5f906-114">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="5f906-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="5f906-115">Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="5f906-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
