---
title: Сбои при проверке безопасности и проверке подлинности
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d7964c59f28f33d6ec7bc3ba605b84e6a201b14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="819ff-102">Сбои при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="819ff-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="819ff-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="819ff-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="819ff-104">Описание</span><span class="sxs-lookup"><span data-stu-id="819ff-104">Description</span></span>  
 <span data-ttu-id="819ff-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="819ff-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="819ff-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="819ff-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="819ff-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="819ff-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="819ff-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="819ff-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="819ff-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="819ff-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="819ff-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="819ff-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="819ff-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="819ff-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="819ff-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="819ff-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="819ff-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="819ff-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
