---
title: Azure Active Directory
description: Создание архитектуры облачных приложений .NET для Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 207043507a9052c47683383a98cef6417a1a2740
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840733"
---
# <a name="azure-active-directory"></a><span data-ttu-id="abdba-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="abdba-103">Azure Active Directory</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="abdba-104">Microsoft Azure Active Directory (Azure AD) предлагает управление удостоверениями и доступом в качестве службы.</span><span class="sxs-lookup"><span data-stu-id="abdba-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="abdba-105">Клиенты используют его для настройки и обслуживания пользователей, сведения о том, какие данные следует хранить, кто имеет доступ к этой информации, кто может управлять ею и какие приложения могут получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="abdba-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="abdba-106">AAD может проверять подлинность пользователей для приложений, настроенных на его использование, обеспечивая единый вход (SSO).</span><span class="sxs-lookup"><span data-stu-id="abdba-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="abdba-107">Его можно использовать самостоятельно или интегрировать с Windows AD на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="abdba-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="abdba-108">Azure AD создается для облака.</span><span class="sxs-lookup"><span data-stu-id="abdba-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="abdba-109">Это действительно решение для идентификации в облаке, которое использует API Graph и синтаксис OData на основе запросов, в отличие от Windows AD, где используется протокол LDAP.</span><span class="sxs-lookup"><span data-stu-id="abdba-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="abdba-110">Локальные Active Directory могут синхронизировать атрибуты пользователей с облаком с помощью служб синхронизации удостоверений, что позволяет выполнять всю проверку подлинности в облаке с помощью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="abdba-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="abdba-111">Кроме того, можно настроить проверку подлинности с помощью Connect для передачи в локальную Active Directory через ADFS для локального выполнения в Windows AD.</span><span class="sxs-lookup"><span data-stu-id="abdba-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="abdba-112">Azure AD поддерживает экраны входа с фирменной символикой компании, многозаводскую проверку подлинности и облачные прокси приложения, которые используются для предоставления единого входа для приложений, размещенных локально.</span><span class="sxs-lookup"><span data-stu-id="abdba-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="abdba-113">Она предлагает различные виды создания отчетов о безопасности и оповещений.</span><span class="sxs-lookup"><span data-stu-id="abdba-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="abdba-114">Ссылки</span><span class="sxs-lookup"><span data-stu-id="abdba-114">References</span></span>

- [<span data-ttu-id="abdba-115">Платформа Microsoft Identity</span><span class="sxs-lookup"><span data-stu-id="abdba-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="abdba-116">[Назад](authentication-authorization.md)
>[Вперед](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="abdba-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
