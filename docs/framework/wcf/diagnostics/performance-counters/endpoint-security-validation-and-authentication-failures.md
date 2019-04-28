---
title: 'Конечная точка: Сбои при проверке безопасности и проверке подлинности'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: e69549a276e2f9cece966dd44f6a1b3a3d3cb59f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916335"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="82d1f-102">Конечная точка: Сбои при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="82d1f-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="82d1f-103">Имя счетчика: Сбои при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="82d1f-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="82d1f-104">Описание</span><span class="sxs-lookup"><span data-stu-id="82d1f-104">Description</span></span>  
 <span data-ttu-id="82d1f-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="82d1f-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="82d1f-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="82d1f-106">Such problems include:</span></span>  
  
- <span data-ttu-id="82d1f-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="82d1f-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="82d1f-108">Токен клиента не прошел проверку подлинности (неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="82d1f-108">Client token has failed authentication (bad password).</span></span>  
  
- <span data-ttu-id="82d1f-109">Сбой при проверке подписи (сообщение было изменено).</span><span class="sxs-lookup"><span data-stu-id="82d1f-109">Signature verification has failed (the message has been tampered).</span></span>  
  
- <span data-ttu-id="82d1f-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="82d1f-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="82d1f-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="82d1f-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="82d1f-112">В сообщении отсутствуют некоторые обязательные элементы (отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="82d1f-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="82d1f-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="82d1f-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
