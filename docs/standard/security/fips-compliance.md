---
title: Соответствие FIPS — .NET Core
description: Описывает соответствие стандартам федеральной информационной обработки (FIPS) .NET Core.
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: 84d6edc6975af0484bb67999ad5891eaf4db057d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626962"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="4df0a-103">Соответствие стандарту федеральной обработки информации (FIPS) .NET Core</span><span class="sxs-lookup"><span data-stu-id="4df0a-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="4df0a-104">Версия федерального стандарта обработки информации (FIPS) 140-2 — это стандарт правительства США, который определяет минимальные требования к безопасности для криптографических модулей в продуктах информационных технологий, как определено в разделе 5131 информации. Новые функции управления технологиями — 1996.</span><span class="sxs-lookup"><span data-stu-id="4df0a-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="4df0a-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="4df0a-105">.NET Core:</span></span>

* <span data-ttu-id="4df0a-106">Передает вызовы примитивов шифрования в стандартные модули, предоставляемые базовой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="4df0a-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="4df0a-107">**Не** обеспечивает использование алгоритмов и размеров ключей, утвержденных FIPS, в приложениях .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4df0a-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="4df0a-108">Системный администратор несет ответственность за настройку соответствия FIPS для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4df0a-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="4df0a-109">Если код написан для совместимой с FIPS среды, разработчик несет ответственность за то, чтобы не использовать несоответствующие алгоритмы FIPS.</span><span class="sxs-lookup"><span data-stu-id="4df0a-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="4df0a-110">Дополнительные сведения о соответствии требованиям FIPS см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="4df0a-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="4df0a-111">Соответствие требованиям Windows FIPS</span><span class="sxs-lookup"><span data-stu-id="4df0a-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="4df0a-112">Настройка Windows для соответствия требованиям FIPS</span><span class="sxs-lookup"><span data-stu-id="4df0a-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="4df0a-113">Глава 8. Федеральные стандарты и нормативы Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="4df0a-113">Chapter 8. Federal Standards and Regulations Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
