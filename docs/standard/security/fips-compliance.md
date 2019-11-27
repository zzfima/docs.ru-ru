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
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>Соответствие стандарту федеральной обработки информации (FIPS) .NET Core

Версия федерального стандарта обработки информации (FIPS) 140-2 — это стандарт правительства США, который определяет минимальные требования к безопасности для криптографических модулей в продуктах информационных технологий, как определено в разделе 5131 информации. Новые функции управления технологиями — 1996.

.NET Core:

* Передает вызовы примитивов шифрования в стандартные модули, предоставляемые базовой операционной системой.
* **Не** обеспечивает использование алгоритмов и размеров ключей, утвержденных FIPS, в приложениях .NET Core.

Системный администратор несет ответственность за настройку соответствия FIPS для операционной системы.

Если код написан для совместимой с FIPS среды, разработчик несет ответственность за то, чтобы не использовать несоответствующие алгоритмы FIPS.

Дополнительные сведения о соответствии требованиям FIPS см. в следующих статьях:

* [Соответствие требованиям Windows FIPS](/windows/security/threat-protection/fips-140-validation)
* [Настройка Windows для соответствия требованиям FIPS](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [10,2. ФЕДЕРАЛЬНЫЙ СТАНДАРТ ОБРАБОТКИ ИНФОРМАЦИИ (FIPS)](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
