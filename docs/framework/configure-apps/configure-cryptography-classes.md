---
title: "Настройка криптографических классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 23bd6007beb870895316a565283ee7e7354c931b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="67112-102">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="67112-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="67112-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Позволяет администраторам компьютера настраивать алгоритмы шифрования по умолчанию и реализации алгоритма, используемые в .NET Framework и соответствующих приложениях.</span><span class="sxs-lookup"><span data-stu-id="67112-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="67112-104">Например, предприятие, в котором есть собственная реализация алгоритма шифрования ее можно использовать значение по умолчанию вместо реализации [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67112-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="67112-105">Несмотря на то, что управляемые приложения, использующие шифрование, всегда можно явно привязать к конкретной реализации, рекомендуется, чтобы они создавали криптографические объекты с помощью системы настройки шифрования.</span><span class="sxs-lookup"><span data-stu-id="67112-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67112-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="67112-106">In This Section</span></span>  
 [<span data-ttu-id="67112-107">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="67112-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="67112-108">Описывает сопоставления имени алгоритма с криптографическим классом.</span><span class="sxs-lookup"><span data-stu-id="67112-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="67112-109">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="67112-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="67112-110">Описание способов сопоставления идентификатора объекта в криптографическому алгоритму.</span><span class="sxs-lookup"><span data-stu-id="67112-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="67112-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="67112-111">Related Sections</span></span>  
 [<span data-ttu-id="67112-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="67112-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="67112-113">Общие сведения о криптографических служб, предоставляемых [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67112-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="67112-114">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="67112-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="67112-115">Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="67112-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
