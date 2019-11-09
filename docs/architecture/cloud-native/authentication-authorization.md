---
title: Проверка подлинности и авторизация в собственных облачных приложениях
description: Создание архитектуры облачных приложений .NET для Azure | Проверка подлинности и авторизация в собственных облачных приложениях
ms.date: 06/30/2019
ms.openlocfilehash: a397175e98c2e8103d2a8c372c81fcca65f19b11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840751"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="82d89-103">Проверка подлинности и авторизация в приложениях, ориентированных на облако</span><span class="sxs-lookup"><span data-stu-id="82d89-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="82d89-104">*Проверка подлинности* — это процесс определения удостоверения субъекта безопасности.</span><span class="sxs-lookup"><span data-stu-id="82d89-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="82d89-105">*Авторизация* — это действие предоставления участнику, прошедшему проверку подлинности, разрешения на выполнение действия или доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="82d89-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="82d89-106">Иногда проверка подлинности сокращается до `AuthN`, а авторизация сокращается до `AuthZ`.</span><span class="sxs-lookup"><span data-stu-id="82d89-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="82d89-107">Облачные приложения должны использовать открытые протоколы на основе HTTP для проверки подлинности субъектов безопасности, так как как клиенты, так и приложения могут работать в любой точке мира на любой платформе или устройстве.</span><span class="sxs-lookup"><span data-stu-id="82d89-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="82d89-108">Единственный общий фактор — HTTP.</span><span class="sxs-lookup"><span data-stu-id="82d89-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="82d89-109">Многие организации по-прежнему используют локальные службы проверки подлинности, такие как службы федерации Active Directory (AD FS) (ADFS).</span><span class="sxs-lookup"><span data-stu-id="82d89-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="82d89-110">Хотя этот подход традиционно обслуживается организациями в целях локальной аутентификации, облачные приложения получают преимущества от систем, разработанных специально для облака.</span><span class="sxs-lookup"><span data-stu-id="82d89-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="82d89-111">В последних 2019 рекомендациях по обеспечению безопасности National кибератак Security Center (NCSC) для организаций, использующих Azure AD в качестве основного источника проверки подлинности, снижается риск по сравнению с ADFS.</span><span class="sxs-lookup"><span data-stu-id="82d89-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="82d89-112">Ниже приведены некоторые причины, описанные в [этом анализе](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) .</span><span class="sxs-lookup"><span data-stu-id="82d89-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="82d89-113">Доступ к полному набору технологий защиты учетных данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="82d89-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="82d89-114">Большинство организаций уже полагается на Azure AD в некоторый экстент.</span><span class="sxs-lookup"><span data-stu-id="82d89-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="82d89-115">Двойное хэширование хэшей NTLM гарантирует, что компрометация не позволит использовать учетные данные, работающие в локальной Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82d89-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="82d89-116">Ссылки</span><span class="sxs-lookup"><span data-stu-id="82d89-116">References</span></span>

- [<span data-ttu-id="82d89-117">Основы проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="82d89-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="82d89-118">Маркеры доступа и утверждения</span><span class="sxs-lookup"><span data-stu-id="82d89-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="82d89-119">Может быть пора выделить свои локальные службы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="82d89-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="82d89-120">[Назад](identity.md)
>[Вперед](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="82d89-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
