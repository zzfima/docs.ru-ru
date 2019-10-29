---
title: Пользовательские обработчики маркеров
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
ms.openlocfilehash: ccf794b4c229bbc9b40ae7ec2fd649825122cecf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040558"
---
# <a name="custom-token-handlers"></a><span data-ttu-id="f0306-102">Пользовательские обработчики маркеров</span><span class="sxs-lookup"><span data-stu-id="f0306-102">Custom Token Handlers</span></span>
<span data-ttu-id="f0306-103">В этом разделе описываются обработчики маркеров на платформе WIF и рассказывается о том, как использовать их для обработки маркеров.</span><span class="sxs-lookup"><span data-stu-id="f0306-103">This topic discusses token handlers in WIF and how they are used to process tokens.</span></span> <span data-ttu-id="f0306-104">Кроме того, здесь рассматривается, что необходимо для создания пользовательских обработчиков для типов маркеров, которые по умолчанию не поддерживаются на платформе WIF.</span><span class="sxs-lookup"><span data-stu-id="f0306-104">The topic also covers what is necessary to create custom token handlers for token types that are not supported by default in WIF.</span></span>  
  
## <a name="introduction-to-token-handlers-in-wif"></a><span data-ttu-id="f0306-105">Общие сведения об обработчиках маркеров на платформе WIF</span><span class="sxs-lookup"><span data-stu-id="f0306-105">Introduction to Token Handlers in WIF</span></span>  
 <span data-ttu-id="f0306-106">На платформе WIF предусмотрены обработчики маркеров безопасности, которые используются для создания, чтения, записи и проверки маркеров для приложения проверяющей стороны и службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0306-106">WIF relies on security token handlers to create, read, write, and validate tokens for a relying party (RP) application or a security token service (STS).</span></span> <span data-ttu-id="f0306-107">Обработчики маркеров — это точки расширения, в которых вы можете добавлять на конвейер WIF пользовательские обработчики или настраивать поведение существующих обработчиков.</span><span class="sxs-lookup"><span data-stu-id="f0306-107">Token handlers are extensibility points for you to add a custom token handler in the WIF pipeline, or to customize the way that an existing token handler manages tokens.</span></span> <span data-ttu-id="f0306-108">На платформе WIF представлено девять встроенных обработчиков маркеров безопасности, которые при необходимости можно изменить или полностью переопределить.</span><span class="sxs-lookup"><span data-stu-id="f0306-108">WIF provides nine built-in security token handlers that can be modified or entirely overridden to change the functionality as necessary.</span></span>  
  
## <a name="built-in-security-token-handlers-in-wif"></a><span data-ttu-id="f0306-109">Встроенные обработчики маркеров безопасности на платформе WIF</span><span class="sxs-lookup"><span data-stu-id="f0306-109">Built-In Security Token Handlers in WIF</span></span>  
 <span data-ttu-id="f0306-110">На платформе WIF 4.5 представлено девять классов для обработчиков маркеров безопасности, которые являются производными от абстрактного базового класса <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span><span class="sxs-lookup"><span data-stu-id="f0306-110">WIF 4.5 includes nine security token handler classes that derive from the abstract base class <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span></span>  
  
- <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a><span data-ttu-id="f0306-111">Добавление пользовательского обработчика маркеров</span><span class="sxs-lookup"><span data-stu-id="f0306-111">Adding a Custom Token Handler</span></span>  
 <span data-ttu-id="f0306-112">Для маркеров некоторых типов, таких как простые веб-маркеры (SWT) и веб-маркеры JSON (JWT), на платформе WIF не предусмотрены встроенные обработчики.</span><span class="sxs-lookup"><span data-stu-id="f0306-112">Some token types, such as Simple Web Tokens (SWT) and JSON Web Tokens (JWT) do not have built-in token handlers provided by WIF.</span></span> <span data-ttu-id="f0306-113">Для таких маркеров и других маркеров, для которых отсутствует встроенный обработчик, необходимо создать пользовательский обработчик, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f0306-113">For these token types and for others that do not have a built-in handler, you need to perform the following steps to create a custom token handler.</span></span>  
  
#### <a name="adding-a-custom-token-handler"></a><span data-ttu-id="f0306-114">Добавление пользовательского обработчика маркеров</span><span class="sxs-lookup"><span data-stu-id="f0306-114">Adding a custom token handler</span></span>  
  
1. <span data-ttu-id="f0306-115">Создайте новый класс, производный от <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="f0306-115">Create a new class that derives from <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span></span>  
  
2. <span data-ttu-id="f0306-116">Переопределите следующие методы и предоставьте их собственную реализацию:</span><span class="sxs-lookup"><span data-stu-id="f0306-116">Override the following methods and provide your own implementation:</span></span>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3. <span data-ttu-id="f0306-117">Добавьте ссылку на новый пользовательский обработчик маркеров в файл *Web.config* или *App.config* в разделе **\<system.identityModel>** , который определяет параметры платформы WIF.</span><span class="sxs-lookup"><span data-stu-id="f0306-117">Add a reference to the new custom token handler in the *Web.config* or *App.config* file, within the **\<system.identityModel>** section that applies to WIF.</span></span> <span data-ttu-id="f0306-118">Например, следующая разметка конфигурации задает новый обработчик маркеров **MyCustomTokenHandler**, который размещается в пространстве имен **CustomToken**.</span><span class="sxs-lookup"><span data-stu-id="f0306-118">For example, the following configuration markup specifies a new token handler named **MyCustomTokenHandler** that resides in the **CustomToken** namespace.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     <span data-ttu-id="f0306-119">Обратите внимание, что при определении собственного обработчика маркеров для типов маркеров со встроенным обработчиком необходимо добавить **элемент \<remove>** , чтобы исключить обработчик по умолчанию и использовать вместо него собственный.</span><span class="sxs-lookup"><span data-stu-id="f0306-119">Note that if you are providing your own token handler to handle a token type that already has a built-in token handler, you need to add a **\<remove>** element to drop the default handler and use your custom handler instead.</span></span> <span data-ttu-id="f0306-120">Например, в следующей конфигурации <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> заменяется пользовательским обработчиком маркеров:</span><span class="sxs-lookup"><span data-stu-id="f0306-120">For example, the following configuration replaces the default <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> with the custom token handler:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789" />  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
