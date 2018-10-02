---
title: 'Конечная точка: количество сбоев при проверке безопасности и проверке подлинности'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
ms.openlocfilehash: f7cd2268eefa0176ab71a3d5d3bc82c178664742
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862806"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="60986-102">Конечная точка: количество сбоев при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="60986-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="60986-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="60986-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="60986-104">Описание</span><span class="sxs-lookup"><span data-stu-id="60986-104">Description</span></span>  
 <span data-ttu-id="60986-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="60986-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="60986-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="60986-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="60986-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="60986-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="60986-108">Токен клиента не прошел проверку подлинности (неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="60986-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="60986-109">Сбой при проверке подписи (сообщение было изменено).</span><span class="sxs-lookup"><span data-stu-id="60986-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="60986-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="60986-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="60986-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="60986-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="60986-112">В сообщении отсутствуют некоторые обязательные элементы (отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="60986-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="60986-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="60986-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
