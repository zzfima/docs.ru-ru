---
title: Как выполнить Создание службы маркеров безопасности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
ms.openlocfilehash: 1d2621b43428fa249fb6ebb820885ebe0a2221f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577262"
---
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="7f015-102">Как выполнить Создание службы маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="7f015-102">How to: Create a Security Token Service</span></span>
<span data-ttu-id="7f015-103">Служба маркеров безопасности реализует протокол, определенный в спецификации WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="7f015-103">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="7f015-104">Данный протокол определяет форматы сообщения и шаблоны обмена сообщениями для выпуска, обновления, отмены и проверки маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f015-104">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="7f015-105">Данная служба маркеров безопасности дает одну или несколько из данных возможностей.</span><span class="sxs-lookup"><span data-stu-id="7f015-105">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="7f015-106">В данном разделе рассматривается наиболее общий сценарий: реализация выпуска маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-106">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="7f015-107">Выпуск маркеров</span><span class="sxs-lookup"><span data-stu-id="7f015-107">Issuing Tokens</span></span>  
 <span data-ttu-id="7f015-108">WS-Trust определяет форматы сообщения на основе элемента схемы `RequestSecurityToken` языка определения схемы XML (XSD) и элемента схемы XSD `RequestSecurityTokenResponse` для выпуска маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-108">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="7f015-109">Кроме того, WS-Trust определяет связанные универсальные коды ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="7f015-109">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="7f015-110">Действия, связанным с `RequestSecurityToken` сообщение `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span><span class="sxs-lookup"><span data-stu-id="7f015-110">The action URI associated with the `RequestSecurityToken` message is `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span></span> <span data-ttu-id="7f015-111">Действия, связанным с `RequestSecurityTokenResponse` сообщение `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span><span class="sxs-lookup"><span data-stu-id="7f015-111">The action URI associated with the `RequestSecurityTokenResponse` message is   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="7f015-112">Структура сообщения с запросом</span><span class="sxs-lookup"><span data-stu-id="7f015-112">Request Message Structure</span></span>  
 <span data-ttu-id="7f015-113">Структура сообщения с запросом на выпуск обычно состоит из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="7f015-113">The issue request message structure typically consists of the following items:</span></span>  
  
-   <span data-ttu-id="7f015-114">Запрос введите URI со значением `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span><span class="sxs-lookup"><span data-stu-id="7f015-114">A request type URI with a value of `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span></span>
  
-   <span data-ttu-id="7f015-115">Универсальный код ресурса (URI) типа маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-115">A token type URI.</span></span> <span data-ttu-id="7f015-116">Для маркеров Security Assertions Markup Language (SAML) 1.1 Этот URI значение `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span><span class="sxs-lookup"><span data-stu-id="7f015-116">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span></span>  
  
-   <span data-ttu-id="7f015-117">Значение размера ключа, указывающее количество битов в ключе, связанное с выпущенным маркером.</span><span class="sxs-lookup"><span data-stu-id="7f015-117">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
-   <span data-ttu-id="7f015-118">Универсальный код ресурса (URI) типа ключа.</span><span class="sxs-lookup"><span data-stu-id="7f015-118">A key type URI.</span></span> <span data-ttu-id="7f015-119">Для симметричных ключей, этот URI значение `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="7f015-119">For symmetric keys, the value of this URI is `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span></span>  
  
 <span data-ttu-id="7f015-120">Кроме того, может присутствовать несколько других элементов.</span><span class="sxs-lookup"><span data-stu-id="7f015-120">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="7f015-121">Материал ключа, предоставленный клиентом.</span><span class="sxs-lookup"><span data-stu-id="7f015-121">Key material provided by the client.</span></span>  
  
-   <span data-ttu-id="7f015-122">Информация об области, показывающая целевую службу, с которой будут использоваться выпущенные маркеры.</span><span class="sxs-lookup"><span data-stu-id="7f015-122">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="7f015-123">При создании ответного сообщения о выпуске служба маркеров безопасности использует информацию письма с запросом на выпуск.</span><span class="sxs-lookup"><span data-stu-id="7f015-123">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="7f015-124">Структура ответного сообщения</span><span class="sxs-lookup"><span data-stu-id="7f015-124">Response Message Structure</span></span>  
 <span data-ttu-id="7f015-125">Структура ответного сообщения о выпуске обычно состоит из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="7f015-125">The issue response message structure typically consists of the following items;</span></span>  
  
-   <span data-ttu-id="7f015-126">Выданный маркер безопасности, например, проверочное утверждение SAML 1.1.</span><span class="sxs-lookup"><span data-stu-id="7f015-126">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
-   <span data-ttu-id="7f015-127">Маркер проверки, связанный с маркером безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f015-127">A proof token associated with the security token.</span></span> <span data-ttu-id="7f015-128">Для симметричных ключей такой маркер часто является зашифрованной формой материала ключа.</span><span class="sxs-lookup"><span data-stu-id="7f015-128">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
-   <span data-ttu-id="7f015-129">Ссылки на выпущенный маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f015-129">References to the issued security token.</span></span> <span data-ttu-id="7f015-130">Обычно служба маркеров безопасности возвращает ссылку, которая может быть использована при появлении выданного маркера в последующем сообщении, отправленном клиентом, и другую ссылку, которая может быть использована, если маркер не присутствует в последующих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7f015-130">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="7f015-131">Кроме того, может присутствовать несколько других элементов.</span><span class="sxs-lookup"><span data-stu-id="7f015-131">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="7f015-132">Материал ключа, предоставленный службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f015-132">Key material provided by the security token service.</span></span>  
  
-   <span data-ttu-id="7f015-133">Алгоритм, необходимый для расчета общего ключа.</span><span class="sxs-lookup"><span data-stu-id="7f015-133">The algorithm needed to compute the shared key.</span></span>  
  
-   <span data-ttu-id="7f015-134">Сведения о времени существования выпущенного маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-134">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="7f015-135">Сообщения с запросом на обработку</span><span class="sxs-lookup"><span data-stu-id="7f015-135">Processing Request Messages</span></span>  
 <span data-ttu-id="7f015-136">Служба маркеров безопасности обрабатывает запросы на выпуск, анализируя различные фрагменты сообщения с запросом и проверяя возможность выпуска маркера, соответствующего запросу.</span><span class="sxs-lookup"><span data-stu-id="7f015-136">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="7f015-137">Перед созданием выпускаемого маркера служба маркеров безопасности должна определить следующее.</span><span class="sxs-lookup"><span data-stu-id="7f015-137">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
-   <span data-ttu-id="7f015-138">Действительно ли запрос является запросом на выпуск маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-138">The request really is a request for a token to be issued.</span></span>  
  
-   <span data-ttu-id="7f015-139">Поддерживает ли служба маркеров безопасности запрошенный тип маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-139">The security token service supports the requested token type.</span></span>  
  
-   <span data-ttu-id="7f015-140">Авторизован ли автор заявки на подачу заявки.</span><span class="sxs-lookup"><span data-stu-id="7f015-140">The requester is authorized to make the request.</span></span>  
  
-   <span data-ttu-id="7f015-141">Может ли служба маркеров безопасности оправдать ожидания автора заявки, относящиеся к материалу ключа.</span><span class="sxs-lookup"><span data-stu-id="7f015-141">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="7f015-142">Две ответственные части создания маркера определяют, каким ключом подписать маркер и при помощи какого ключа зашифровать общий ключ.</span><span class="sxs-lookup"><span data-stu-id="7f015-142">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="7f015-143">Ключ должен быть подписан так, чтобы при предоставлении клиентом ключа целевой службе данная служба могла определить, что маркер был выпущен службой безопасности ключей, которой она доверяет.</span><span class="sxs-lookup"><span data-stu-id="7f015-143">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="7f015-144">Материал ключа должен быть зашифрован так, чтобы целевая служба могла расшифровать данный материал ключа.</span><span class="sxs-lookup"><span data-stu-id="7f015-144">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="7f015-145">Подписывание утверждения SAML включает создание экземпляра <xref:System.IdentityModel.Tokens.SigningCredentials>.</span><span class="sxs-lookup"><span data-stu-id="7f015-145">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="7f015-146">Конструктор для данного класса принимает следующее</span><span class="sxs-lookup"><span data-stu-id="7f015-146">The constructor for this class takes the following:</span></span>  
  
-   <span data-ttu-id="7f015-147"><xref:System.IdentityModel.Tokens.SecurityKey> для ключа, который будет использоваться при подписывании утверждения SAML.</span><span class="sxs-lookup"><span data-stu-id="7f015-147">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
-   <span data-ttu-id="7f015-148">Строка, определяющая используемый алгоритм подписывания.</span><span class="sxs-lookup"><span data-stu-id="7f015-148">A string identifying the signature algorithm to use.</span></span>  
  
-   <span data-ttu-id="7f015-149">Строка, определяющая используемый алгоритм хэш-кода.</span><span class="sxs-lookup"><span data-stu-id="7f015-149">A string identifying the digest algorithm to use.</span></span>  
  
-   <span data-ttu-id="7f015-150">Дополнительно можно указать <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>, определяющий используемый для подписывания утверждения ключ.</span><span class="sxs-lookup"><span data-stu-id="7f015-150">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="7f015-151">Шифрование общего ключа предполагает принятие материала ключа и его шифрование при помощи ключа, который целевая служба сможет использовать для расшифровки общего ключа.</span><span class="sxs-lookup"><span data-stu-id="7f015-151">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="7f015-152">Обычно используется открытый ключ целевой службы.</span><span class="sxs-lookup"><span data-stu-id="7f015-152">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="7f015-153">Кроме того, для зашифрованного ключа необходим идентификатор <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>.</span><span class="sxs-lookup"><span data-stu-id="7f015-153">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="7f015-154">Затем идентификатор <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> используется для создания `SamlSubject` как части `SamlToken`.</span><span class="sxs-lookup"><span data-stu-id="7f015-154">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="7f015-155">Дополнительные сведения см. в разделе [пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7f015-155">For more information, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="7f015-156">Создание ответных сообщений</span><span class="sxs-lookup"><span data-stu-id="7f015-156">Creating Response Messages</span></span>  
 <span data-ttu-id="7f015-157">После обработки службой маркеров безопасности запроса на выпуск и создания для выпуска маркера и ключа проверки должно быть создано ответное сообщение, включающее, по крайней мере, запрошенный маркер, маркер проверки и ссылки выпущенного маркера.</span><span class="sxs-lookup"><span data-stu-id="7f015-157">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="7f015-158">Выпущенный маркер обычно является маркером <xref:System.IdentityModel.Tokens.SamlSecurityToken>, созданным из <xref:System.IdentityModel.Tokens.SamlAssertion>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7f015-158">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="7f015-159">В случае, когда служба маркеров безопасности предоставляет материал общего ключа, маркер проверки создается путем создания <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="7f015-159">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="7f015-160">Дополнительные сведения о том, как построить токен проверки, когда клиент и служба маркеров безопасности предоставляют материал ключа для общего ключа см. в разделе [пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7f015-160">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="7f015-161">Ссылки выпущенного ключа создаются путем создания экземпляров класса <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>.</span><span class="sxs-lookup"><span data-stu-id="7f015-161">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="7f015-162">После этого различные значения сериализуются в ответное сообщение, возвращаемое клиенту.</span><span class="sxs-lookup"><span data-stu-id="7f015-162">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f015-163">Пример</span><span class="sxs-lookup"><span data-stu-id="7f015-163">Example</span></span>  
 <span data-ttu-id="7f015-164">Полный код для службы маркеров безопасности см. в разделе [пример федерации](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7f015-164">For full code for a security token service, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f015-165">См. также</span><span class="sxs-lookup"><span data-stu-id="7f015-165">See also</span></span>
- <xref:System.IdentityModel.Tokens.SigningCredentials>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>
- <xref:System.IdentityModel.Tokens.SamlSecurityToken>
- <xref:System.IdentityModel.Tokens.SamlAssertion>
- <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>
- [<span data-ttu-id="7f015-166">Пример федерации</span><span class="sxs-lookup"><span data-stu-id="7f015-166">Federation Sample</span></span>](../../../../docs/framework/wcf/samples/federation-sample.md)
