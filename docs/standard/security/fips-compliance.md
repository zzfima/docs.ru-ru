---
title: Соответствие FIPS — .NET Core
description: Описывает соответствие стандартам федеральной информационной обработки (FIPS) .NET Core.
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205080"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="1c52a-103">Соответствие стандарту федеральной обработки информации (FIPS) .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c52a-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="1c52a-104">Версия федерального стандарта обработки информации (FIPS) 140-2 — это стандарт правительства США, который определяет минимальные требования к безопасности для криптографических модулей в продуктах информационных технологий, как определено в разделе 5131 информации. Новые функции управления технологиями — 1996.</span><span class="sxs-lookup"><span data-stu-id="1c52a-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="1c52a-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="1c52a-105">.NET Core:</span></span>

* <span data-ttu-id="1c52a-106">Передает вызовы примитивов шифрования в стандартные модули, предоставляемые базовой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="1c52a-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="1c52a-107">**Не** обеспечивает использование алгоритмов и размеров ключей, утвержденных FIPS, в приложениях .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c52a-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="1c52a-108">Системный администратор несет ответственность за настройку соответствия FIPS для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1c52a-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="1c52a-109">Если код написан для совместимой с FIPS среды, разработчик несет ответственность за то, чтобы не использовать несоответствующие алгоритмы FIPS.</span><span class="sxs-lookup"><span data-stu-id="1c52a-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="1c52a-110">Дополнительные сведения о соответствии требованиям FIPS см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="1c52a-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="1c52a-111">Соответствие требованиям Windows FIPS</span><span class="sxs-lookup"><span data-stu-id="1c52a-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="1c52a-112">Настройка Windows для соответствия требованиям FIPS</span><span class="sxs-lookup"><span data-stu-id="1c52a-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="1c52a-113">10,2. ФЕДЕРАЛЬНЫЙ СТАНДАРТ ОБРАБОТКИ ИНФОРМАЦИИ (FIPS)</span><span class="sxs-lookup"><span data-stu-id="1c52a-113">10.2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)</span></span>](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
