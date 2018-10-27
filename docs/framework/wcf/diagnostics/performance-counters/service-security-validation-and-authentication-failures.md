---
title: 'Служба: количество сбоев при проверке безопасности и проверке подлинности'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: ba8da3ae6be6bd089690359f19e153da1e0b54fc
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50039995"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="11410-102">Служба: количество сбоев при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="11410-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="11410-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="11410-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="11410-104">Описание</span><span class="sxs-lookup"><span data-stu-id="11410-104">Description</span></span>  
 <span data-ttu-id="11410-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="11410-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="11410-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="11410-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="11410-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="11410-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="11410-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="11410-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="11410-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="11410-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="11410-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="11410-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="11410-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="11410-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="11410-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="11410-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="11410-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="11410-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
