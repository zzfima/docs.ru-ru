---
title: Время уязвимостей и режим CBC Симметричная расшифровка с помощью заполнения
description: Дополнительные сведения о обнаруживать и устранять уязвимости времени расшифровка симметричного режим сцепления блоков шифра (CBC), с помощью заполнения.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 26f4d19f591ac02d792bebbd648e90b07d84de56
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208694"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="70e35-103">Время уязвимостей и режим CBC Симметричная расшифровка с помощью заполнения</span><span class="sxs-lookup"><span data-stu-id="70e35-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="70e35-104">Корпорация Майкрософт считает, что он больше не безопасно расшифровывать данные, зашифрованные с помощью симметричного шифрования режим сцепления блоков шифра (CBC), если проверяемых заполнения был применен без гарантируя целостность зашифрованных данных, за исключением особых в других обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="70e35-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="70e35-105">Это judgement основан на известные криптографических исследований.</span><span class="sxs-lookup"><span data-stu-id="70e35-105">This judgement is based on currently known cryptographic research.</span></span> 

## <a name="introduction"></a><span data-ttu-id="70e35-106">Вступление</span><span class="sxs-lookup"><span data-stu-id="70e35-106">Introduction</span></span>

<span data-ttu-id="70e35-107">Атаке заполнения oracle — это тип атаки зашифрованные данные, которые позволяет злоумышленнику расшифровать содержимое данных, не зная ключа.</span><span class="sxs-lookup"><span data-stu-id="70e35-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="70e35-108">Oracle ссылается «сообщить» которых дает злоумышленнику информацию о ли действие, которое они исполняется указано правильно, или нет.</span><span class="sxs-lookup"><span data-stu-id="70e35-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="70e35-109">Представьте себе воспроизведение доску или карт игры с дочерним.</span><span class="sxs-lookup"><span data-stu-id="70e35-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="70e35-110">При ее начертания светиться с большой одобрение, так как она полагает, что она является об для хорошей перемещения, которая является oracle.</span><span class="sxs-lookup"><span data-stu-id="70e35-110">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="70e35-111">Как игрок, можно использовать этот oracle для планирования и переместить далее соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="70e35-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="70e35-112">Заполнение составляет определенный термин шифрования.</span><span class="sxs-lookup"><span data-stu-id="70e35-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="70e35-113">Некоторые шифров, которые являются алгоритмы, используемые для шифрования данных, работать на блоки данных, где каждый блок имеет фиксированный размер.</span><span class="sxs-lookup"><span data-stu-id="70e35-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="70e35-114">Если данные, которые требуется зашифровать не самый подходящий размер для заполнения блоков, данные дополняются до ее.</span><span class="sxs-lookup"><span data-stu-id="70e35-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="70e35-115">Множество форм заполнения требуют этого дополнения, чтобы всегда присутствовать, даже если исходная входная последовательность была неправильный размер.</span><span class="sxs-lookup"><span data-stu-id="70e35-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="70e35-116">Это позволяет дополнения, чтобы всегда безопасно удалить при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="70e35-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="70e35-117">Совместное размещение две вещи, реализации программы с oracle заполнения показывает, имеет ли расшифрованные данные допустимым заполнения.</span><span class="sxs-lookup"><span data-stu-id="70e35-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="70e35-118">Oracle может быть что-то сложнее, чем возврат значения с сообщением «Недопустимый заполнение» или более сложное подобный значительно другое время для обработки является допустимым блоком, в отличие от недопустимый блок.</span><span class="sxs-lookup"><span data-stu-id="70e35-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="70e35-119">Блочных шифров другое свойство, которое называется режим, который определяет связь данных в первый блок данных во втором блоке, и так далее.</span><span class="sxs-lookup"><span data-stu-id="70e35-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="70e35-120">Одним из наиболее распространенных режимов является CBC.</span><span class="sxs-lookup"><span data-stu-id="70e35-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="70e35-121">CBC представляет начальное случайное блокировать, известные как вектор инициализации (IV) и объединяет предыдущего блока с результатом статического шифрования, чтобы сделать его таким образом, шифрование и то же сообщение с тем же ключом не всегда позволяет создавать такие же выходные данные зашифрованных.</span><span class="sxs-lookup"><span data-stu-id="70e35-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="70e35-122">Злоумышленник может использовать заполнение oracle, в сочетании с структуру данных CBC, для отправки сообщений слегка измененный код, который предоставляет oracle и сохранить отправка данных, пока oracle уведомляющее правильности данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="70e35-123">Из этого ответа злоумышленник может расшифровать сообщение байт за байтом.</span><span class="sxs-lookup"><span data-stu-id="70e35-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="70e35-124">Современные персональные компьютеры сети имеют такие высокого качества, злоумышленник может обнаружить очень мало (менее 0,1 мс), время различия в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="70e35-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="70e35-125">Приложения, при условии что успешной расшифровки может произойти только в том случае, если данные не подделаны может быть подвержен атакам с помощью средств, предназначенных для наблюдения за различия в успешные и неудачные расшифровки.</span><span class="sxs-lookup"><span data-stu-id="70e35-125">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="70e35-126">Хотя эта разница времени может быть более значительные на некоторых языках или библиотеки, чем другие, теперь полагается, это практические угроз для всех языков и библиотек, когда учитывается ответ сбой приложения.</span><span class="sxs-lookup"><span data-stu-id="70e35-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="70e35-127">Возможность изменить зашифрованные данные и проверить результаты с oracle использует такой атаки.</span><span class="sxs-lookup"><span data-stu-id="70e35-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="70e35-128">Единственным способом, полностью защититься от атак является обнаруживать изменения зашифрованные данные и не будет выполнять каких-либо действий с ним.</span><span class="sxs-lookup"><span data-stu-id="70e35-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="70e35-129">Это стандартный способ сделать это является создание подпись для данных и проверка подписи перед любой операции выполняются.</span><span class="sxs-lookup"><span data-stu-id="70e35-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="70e35-130">Подпись должна поддаваться, не может быть создан злоумышленником, в противном случае они бы изменить зашифрованные данные, а затем вычисления используется новая подпись, на основе измененных данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="70e35-131">Один общий тип с соответствующей сигнатурой называется кода проверки подлинности сообщения хэширования с ключом (HMAC).</span><span class="sxs-lookup"><span data-stu-id="70e35-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="70e35-132">Код HMAC отличается от контрольной суммы, что он принимает секретный ключ, известный только пользователю, формирующего HMAC и проверки его пользователю.</span><span class="sxs-lookup"><span data-stu-id="70e35-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="70e35-133">Даже при отсутствии ключа не могут производить правильный HMAC.</span><span class="sxs-lookup"><span data-stu-id="70e35-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="70e35-134">При получении данных, следует воспользоваться зашифрованные данные, независимо друг от друга вычислений с помощью секретного ключа HMAC вы отправителя общей папки, а затем сравнить вычисляемые HMAC, они отправлены по одному.</span><span class="sxs-lookup"><span data-stu-id="70e35-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="70e35-135">Это сравнение должно быть константой времени, в противном случае вы добавили другой выявить oracle, позволяя другой тип атаки.</span><span class="sxs-lookup"><span data-stu-id="70e35-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="70e35-136">Таким образом использование дополняются блочные шифры CBC безопасно, необходимо объединить их с HMAC (или другой проверки целостности данных), можно проверить с помощью сравнения константном времени, прежде чем для расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="70e35-137">Поскольку все сообщения измененную принимать то же время сумма для получения ответа, не будет атаки.</span><span class="sxs-lookup"><span data-stu-id="70e35-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="70e35-138">Кто является уязвимым</span><span class="sxs-lookup"><span data-stu-id="70e35-138">Who is vulnerable</span></span>

<span data-ttu-id="70e35-139">Эта уязвимость существует управляемый и машинный приложения, которое выполняет свои собственные шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="70e35-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="70e35-140">Сюда входят, например:</span><span class="sxs-lookup"><span data-stu-id="70e35-140">This includes, for example:</span></span>

- <span data-ttu-id="70e35-141">Приложение, которое шифрует файл cookie для расшифровки более поздней версии на сервере.</span><span class="sxs-lookup"><span data-stu-id="70e35-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="70e35-142">Приложение базы данных, которое предоставляет возможности для пользователей, для вставки данных в таблицу, столбцы которых затем расшифрованы лицом.</span><span class="sxs-lookup"><span data-stu-id="70e35-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="70e35-143">Приложения, основанные на шифрование с использованием общего ключа для защиты передачи данных для передачи данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="70e35-144">Приложения, который шифрует и расшифровывает сообщения TLS-туннеля «внутри».</span><span class="sxs-lookup"><span data-stu-id="70e35-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="70e35-145">Обратите внимание, что использование TLS сама по себе может защитит вас в этих сценариях.</span><span class="sxs-lookup"><span data-stu-id="70e35-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="70e35-146">Уязвимого приложения:</span><span class="sxs-lookup"><span data-stu-id="70e35-146">A vulnerable application:</span></span>

- <span data-ttu-id="70e35-147">Расшифровывает данные с помощью шифра CBC режим с режимом заполнения проверяемый, например PKCS #7 или ANSI X.923.</span><span class="sxs-lookup"><span data-stu-id="70e35-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="70e35-148">Выполняет расшифровку без выполнять проверку целостности данных (через MAC или асимметричный цифровой подписи).</span><span class="sxs-lookup"><span data-stu-id="70e35-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="70e35-149">Это также относится к приложениям, построена на базе абстракции поверх этих примитивах, например структуру EnvelopedData Cryptographic Message Syntax (PKCS #7/CMS).</span><span class="sxs-lookup"><span data-stu-id="70e35-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="70e35-150">Связанные проблемные области.</span><span class="sxs-lookup"><span data-stu-id="70e35-150">Related areas of concern</span></span>

<span data-ttu-id="70e35-151">Справочные материалы привело Майкрософт для дальнейшего занимается CBC сообщений, которые заполняются ISO 10126-эквивалент внутренних полей при сообщении имеет структуру, хорошо известных и прогнозируемых нижний колонтитул.</span><span class="sxs-lookup"><span data-stu-id="70e35-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="70e35-152">Например содержимое, подготовленных в соответствии с правилами синтаксиса шифрования XML консорциума W3C и рекомендации по обработке (xmlenc EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="70e35-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="70e35-153">Хотя рекомендации W3C подписал сообщение, а затем зашифровать считается соответствующее во время, теперь рекомендуется всегда делаем шифрование then подписью.</span><span class="sxs-lookup"><span data-stu-id="70e35-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="70e35-154">Разработчики приложений должны всегда учитывать проверка применимости асимметричный ключ подписи, как не задано отношение доверия, присущие между асимметричного ключа и случайное сообщение.</span><span class="sxs-lookup"><span data-stu-id="70e35-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="70e35-155">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="70e35-155">Details</span></span>

<span data-ttu-id="70e35-156">Исторически произошел согласие, очень важно для шифрования и проверки подлинности с помощью средств подписи HMAC или RSA важных данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="70e35-157">Однако было меньше четкие инструкции о том, как последовательность операций шифрования и проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="70e35-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="70e35-158">Из-за уязвимости, описанные в этой статье рекомендации корпорации Майкрософт — теперь всегда использовать парадигма «шифрование then подписью».</span><span class="sxs-lookup"><span data-stu-id="70e35-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="70e35-159">То есть сначала шифрование данных с помощью симметричного ключа, а затем вычислений MAC или асимметричной подписи над зашифрованного текста (зашифрованных данных).</span><span class="sxs-lookup"><span data-stu-id="70e35-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="70e35-160">При расшифровке данных, выполните обратное.</span><span class="sxs-lookup"><span data-stu-id="70e35-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="70e35-161">Во-первых Подтвердите MAC или подписи зашифрованного текста, а затем расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="70e35-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="70e35-162">Класс уязвимостей, известные как «padding атак oracle» известно, что существует более 10 лет.</span><span class="sxs-lookup"><span data-stu-id="70e35-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="70e35-163">Эти уязвимости злоумышленник может расшифровать данные, зашифрованные блок симметричные алгоритмы, например AES и 3DES, используя не более 4096 попыток каждого блока данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="70e35-164">Сделать эти уязвимости использование тот факт, что блок шифры чаще всего используются с данными проверяемый заполнения в конце.</span><span class="sxs-lookup"><span data-stu-id="70e35-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="70e35-165">Найден, что если злоумышленник может незаконно зашифрованных данных и выяснить ли изменение данных вызвала ошибку в формате заполнения в конце, злоумышленник может расшифровать данные.</span><span class="sxs-lookup"><span data-stu-id="70e35-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="70e35-166">Изначально практические атак были основаны на службы, которые будут возвращать различные коды ошибок зависимости от того, было ли заполнение правильной, например уязвимость ASP.NET [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span><span class="sxs-lookup"><span data-stu-id="70e35-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="70e35-167">Тем не менее Корпорация Майкрософт теперь считает, что это целесообразно провести аналогичные атак с использованием только различия по синхронизации между обработки допустимые и недопустимые заполнения.</span><span class="sxs-lookup"><span data-stu-id="70e35-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="70e35-168">Если подпись использует схему шифрования, а, проверка подписи выполняется с предопределенной среды выполнения для данной длины данных (независимо от содержимого), без передачи сведений, можно проверить целостность данных Злоумышленник через [канала со стороны](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="70e35-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="70e35-169">Поскольку проверка целостности отклоняет все измененные сообщения, угроза oracle заполнения устраняется.</span><span class="sxs-lookup"><span data-stu-id="70e35-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="70e35-170">Руководство</span><span class="sxs-lookup"><span data-stu-id="70e35-170">Guidance</span></span>

<span data-ttu-id="70e35-171">Первое и самое главное Корпорация Майкрософт рекомендует, что все данные, имеющие конфиденциальность должен передаваться через Transport Layer Security (TLS), преемник для Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="70e35-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="70e35-172">Далее проанализируйте приложение:</span><span class="sxs-lookup"><span data-stu-id="70e35-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="70e35-173">Понять, какие шифрование, выполняемой и точно какие Шифрование обеспечивается корпорацией платформ и API, вы используете.</span><span class="sxs-lookup"><span data-stu-id="70e35-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="70e35-174">Быть что каждого использования на каждом уровне симметричный [алгоритм шифрования блока](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), таких как AES и 3DES, в режиме CBC включить использование проверку целостности данных с закрытым ключом (асимметричной подписи HMAC или изменить режим шифрования для [шифрования с проверкой подлинности](https://en.wikipedia.org/wiki/Authenticated_encryption) режим (AE), например GCM или CCM).</span><span class="sxs-lookup"><span data-stu-id="70e35-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="70e35-175">На основании текущего research, обычно считается, если действия проверки подлинности и шифрования выполняются независимо друг от друга не AE режимов шифрования, проверки подлинности зашифрованного текста (шифрование, затем знак) вариант является наилучшим Общие.</span><span class="sxs-lookup"><span data-stu-id="70e35-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="70e35-176">Однако не универсальными правильный ответ на шифрование и из этого общего правила не так хороши, как расширенный астера специалистов опыта криптограф.</span><span class="sxs-lookup"><span data-stu-id="70e35-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="70e35-177">Приложения, которые не могут изменять их формат сообщений, но без проверки подлинности CBC расшифровки рекомендуется пытаться добавить исправлений, такие как:</span><span class="sxs-lookup"><span data-stu-id="70e35-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="70e35-178">Расшифровка не позволяя дешифратор для проверьте или удалите заполнения:</span><span class="sxs-lookup"><span data-stu-id="70e35-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="70e35-179">Заполнение, которое было применено по-прежнему должны быть удалены или пропущены, перемещении нагрузку в приложение.</span><span class="sxs-lookup"><span data-stu-id="70e35-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="70e35-180">Преимуществом является то, что заполнение проверки и удаления могут быть внедрены в другую логику проверки данных приложения.</span><span class="sxs-lookup"><span data-stu-id="70e35-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="70e35-181">При проверке заполнения и проверке данных может осуществляться в константном времени, уменьшается угроз.</span><span class="sxs-lookup"><span data-stu-id="70e35-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="70e35-182">Поскольку Интерпретация заполнение изменяется длина предполагаемых сообщения, по-прежнему возможно сведения о времени, извлекаемыми из этого подхода.</span><span class="sxs-lookup"><span data-stu-id="70e35-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="70e35-183">Измените режим заполнения расшифровки ISO10126:</span><span class="sxs-lookup"><span data-stu-id="70e35-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="70e35-184">Заполнение расшифровки ISO10126 совместим с заполнение шифрования PKCS7 и заполнения ANSIX923 шифрования.</span><span class="sxs-lookup"><span data-stu-id="70e35-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="70e35-185">Изменение режима уменьшает знаний oracle заполнения на 1 байт, а не весь блок.</span><span class="sxs-lookup"><span data-stu-id="70e35-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="70e35-186">Однако если содержимое имеет известный нижний колонтитул, например, закрывающий XML-элемент связанных атак можно продолжить взломать оставшуюся часть сообщения.</span><span class="sxs-lookup"><span data-stu-id="70e35-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="70e35-187">Это также не предотвращает восстановления открытого текста в ситуациях, когда злоумышленник удерживающей открытого текста для шифрования несколько раз со смещением другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="70e35-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="70e35-188">Шлюз оценки для расшифровки вызова ослабить сигнал о времени:</span><span class="sxs-lookup"><span data-stu-id="70e35-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="70e35-189">Вычисление времени ожидания должно быть не менее сверх максимальное количество времени, могут быть выполнены операции расшифровки для любой сегмент данных, содержащий заполнения.</span><span class="sxs-lookup"><span data-stu-id="70e35-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="70e35-190">Время вычисления должны выполняться в соответствии с инструкциями в статье [получения отметки времени с высоким разрешением](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), не с помощью <xref:System.Environment.TickCount?displayProperty=nameWithType> (с учетом данных наката over или переполнение) или вычитание двух меток времени системы (изменены NTP ошибки).</span><span class="sxs-lookup"><span data-stu-id="70e35-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="70e35-191">Время вычислений необходимо включающие операции дешифрования, включая все возможные исключения в управлять или приложений C++, добавленными не только в конце.</span><span class="sxs-lookup"><span data-stu-id="70e35-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="70e35-192">При успешном или неуспешном завершении будет определено еще, шлюз времени должно возвратить сбой после истечения срока его действия.</span><span class="sxs-lookup"><span data-stu-id="70e35-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="70e35-193">Службы, выполняющих расшифровка без проверки подлинности должны иметь средств мониторинга для обнаружения, что поток сообщения «Недопустимый» будет подключена.</span><span class="sxs-lookup"><span data-stu-id="70e35-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="70e35-194">Не забывайте, что этот сигнал выполняет ложных положительных результатов (основаниях поврежденные данные) и ложных отрицательных результатов (рассредоточения атаки на достаточно продолжительное время, чтобы избежать обнаружения).</span><span class="sxs-lookup"><span data-stu-id="70e35-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="70e35-195">Чтобы найти уязвимым - приложений в машинном коде</span><span class="sxs-lookup"><span data-stu-id="70e35-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="70e35-196">Для программ, которые построены на шифрование Windows: библиотеки следующего поколения (CNG):</span><span class="sxs-lookup"><span data-stu-id="70e35-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="70e35-197">Вызов расшифровки [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), указав `BCRYPT_BLOCK_PADDING` флаг.</span><span class="sxs-lookup"><span data-stu-id="70e35-197">The decryption call is to [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="70e35-198">Дескриптор ключа был инициализирован путем вызова [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) с [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) значение `BCRYPT_CHAIN_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="70e35-198">The key handle has been initialized by calling [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="70e35-199">Поскольку `BCRYPT_CHAIN_MODE_CBC` используется по умолчанию, затронутых код не может иметь присвоено любое значение для `BCRYPT_CHAINING_MODE`.</span><span class="sxs-lookup"><span data-stu-id="70e35-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="70e35-200">Для программ, созданных для старых API шифрования Windows:</span><span class="sxs-lookup"><span data-stu-id="70e35-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="70e35-201">Вызов расшифровки [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) с `Final=TRUE`.</span><span class="sxs-lookup"><span data-stu-id="70e35-201">The decryption call is to [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) with `Final=TRUE`.</span></span>
- <span data-ttu-id="70e35-202">Дескриптор ключа был инициализирован путем вызова [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) с [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) значение `CRYPT_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="70e35-202">The key handle has been initialized by calling [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="70e35-203">Поскольку `CRYPT_MODE_CBC` используется по умолчанию, затронутых код не может иметь присвоено любое значение для `KP_MODE`.</span><span class="sxs-lookup"><span data-stu-id="70e35-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="70e35-204">Поиск кода уязвимым - управляемых приложений</span><span class="sxs-lookup"><span data-stu-id="70e35-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="70e35-205">Вызов расшифровки <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> или <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> методы <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70e35-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="70e35-206">Это включает в себя следующие производные типы в .NET, но может также включать сторонним типам:</span><span class="sxs-lookup"><span data-stu-id="70e35-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <span data-ttu-id="70e35-207"><xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Было задано значение <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, или <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70e35-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="70e35-208">Поскольку <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> используется по умолчанию, затронутых кода никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="70e35-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="70e35-209"><xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Было задано значение <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="70e35-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="70e35-210">Поскольку <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> используется по умолчанию, затронутых кода никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="70e35-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="70e35-211">Чтобы найти уязвимым - синтаксиса шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="70e35-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="70e35-212">Сообщение CMS EnvelopedData без проверки подлинности, которого зашифрованное содержимое использует режим CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), (1.3.14.3.2.7) DES, 3DES (1.2.840.113549.3.7) или версии-кандидата 2 (1.2.840.113549.3.2) — уязвимости, также как и в случае сообщений с помощью других алгоритмов шифрования блока в режиме CBC.</span><span class="sxs-lookup"><span data-stu-id="70e35-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="70e35-213">Пока потоковых шифров не подвержены данной уязвимости, корпорация Майкрософт рекомендует всегда проверку подлинности данные по проверке ContentEncryptionAlgorithm значение.</span><span class="sxs-lookup"><span data-stu-id="70e35-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="70e35-214">Для управляемых приложений EnvelopedData CMS, больших двоичных объектов может быть обнаружено как любое значение, которое передается <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="70e35-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="70e35-215">Для собственных приложений большой двоичный объект CMS EnvelopedData могут быть обнаружены как любое значение, указанное в дескриптор CMS через [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) , что приводит к [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) — `CMSG_ENVELOPED` и/или дескриптор CMS затем отправляются `CMSG_CTRL_DECRYPT` инструкция через [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span><span class="sxs-lookup"><span data-stu-id="70e35-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) whose resulting [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="70e35-216">Пример кода уязвим - управляемые</span><span class="sxs-lookup"><span data-stu-id="70e35-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="70e35-217">Этот метод считывает файл cookie и расшифровывает его, и отображается без проверки целостности данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="70e35-218">Таким образом содержимое файла cookie, который считывается с помощью данного метода могут подвергнуться атаке пользователь, получивший его или любой злоумышленник получил значение зашифрованного файла cookie.</span><span class="sxs-lookup"><span data-stu-id="70e35-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="70e35-219">Следующий пример кода рекомендуется выполнять-управляемые</span><span class="sxs-lookup"><span data-stu-id="70e35-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="70e35-220">В следующем примере кода используется формат нестандартные сообщения</span><span class="sxs-lookup"><span data-stu-id="70e35-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="70e35-221">где `cipher_algorithm_id` и `hmac_algorithm_id` идентификаторы алгоритмов являются локальными для приложения (стандартным) представлениями этих алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="70e35-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="70e35-222">Эти идентификаторы смысл в других частях вашей существующей протокол обмена сообщениями, а не как состояния системы объединенных потока данных.</span><span class="sxs-lookup"><span data-stu-id="70e35-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="70e35-223">В этом примере также использует только один главный ключ для получения ключа шифрования и ключ HMAC.</span><span class="sxs-lookup"><span data-stu-id="70e35-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="70e35-224">Это обеспечивается как для удобства для включения приложения, ключом которых является отдельным элементом в приложение с ключами двумя, а также чтобы стимулировать два ключа для сохранения значений как разные.</span><span class="sxs-lookup"><span data-stu-id="70e35-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="70e35-225">Он дальнейшей гарантирует, что ключ HMAC и ключ шифрования не удается получить не синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="70e35-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="70e35-226">В этом примере не принимает <xref:System.IO.Stream> для шифрования или расшифровки.</span><span class="sxs-lookup"><span data-stu-id="70e35-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="70e35-227">Текущий делает формат данных один проход шифрования сложно из-за `hmac_tag` значение предшествует зашифрованного текста.</span><span class="sxs-lookup"><span data-stu-id="70e35-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="70e35-228">Тем не менее этот формат был выбран, поскольку он поддерживает все элементы фиксированного размера с самого начала, чтобы сделать проще, средство синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="70e35-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="70e35-229">Формат данных расшифровка один проход возможна на то, что разработчик cautioned для вызова GetHashAndReset и проверить результаты перед вызовом TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="70e35-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="70e35-230">Если потокового шифрования является важной, в другом режиме AE будут отличаться.</span><span class="sxs-lookup"><span data-stu-id="70e35-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
