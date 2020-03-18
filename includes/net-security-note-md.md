---
ms.openlocfilehash: f70452cbadc8927521f0fcfda693586c277e4d0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "70041160"
---
> [!CAUTION]
> <span data-ttu-id="4318b-101">Управление доступом для кода и частично доверенный код</span><span class="sxs-lookup"><span data-stu-id="4318b-101">Code Access Security and Partially Trusted Code</span></span>
>
> <span data-ttu-id="4318b-102">Платформа .NET Framework предоставляет механизм для принудительного применения различных уровней доверия к разным частям кода, выполняемым в одном и том же приложении. Этот механизм называется управлением доступом для кода.</span><span class="sxs-lookup"><span data-stu-id="4318b-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="4318b-103">Управление доступом для кода в .NET Framework не следует использовать в качестве механизма обеспечения границ безопасности на основе происхождения кода или других аспектов, связанных с удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="4318b-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="4318b-104">Мы обновляем рекомендации с учетом того, что управление доступом для кода и прозрачный для системы безопасности код не будут поддерживаться в качестве механизма безопасности при работе с частично доверенным кодом, особенно с кодом неизвестного происхождения.</span><span class="sxs-lookup"><span data-stu-id="4318b-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="4318b-105">Мы не рекомендуем загружать и выполнять код из неизвестных источников, не предприняв дополнительные меры безопасности.</span><span class="sxs-lookup"><span data-stu-id="4318b-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="4318b-106">Эта политика действует в отношении всех версий платформы .NET Framework, кроме платформы .NET Framework в составе Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4318b-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
