---
title: Сбои при проверке безопасности и проверке подлинности
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
ms.openlocfilehash: d13e94800d71c6f567c6aab61974e42b1a3f1706
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070946"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="b7e44-102">Сбои при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="b7e44-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="b7e44-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="b7e44-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="b7e44-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b7e44-104">Description</span></span>  
 <span data-ttu-id="b7e44-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="b7e44-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="b7e44-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="b7e44-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="b7e44-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="b7e44-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="b7e44-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="b7e44-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="b7e44-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="b7e44-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="b7e44-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="b7e44-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="b7e44-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="b7e44-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="b7e44-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="b7e44-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="b7e44-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="b7e44-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
