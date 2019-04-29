---
title: Уязвимости в учете времени при симметричной расшифровке в режиме CBC с использованием заполнения
description: Узнайте, как для обнаружения и устранения уязвимостей, о времени с помощью Симметричная расшифровка режим сцепления блоков шифра (CBC) с помощью заполнения.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 6d8c2593cdbc4bbff2b1507196989282b16aa9a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933904"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="611d7-103">Уязвимости в учете времени при симметричной расшифровке в режиме CBC с использованием заполнения</span><span class="sxs-lookup"><span data-stu-id="611d7-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="611d7-104">Корпорация Майкрософт считает, что он больше не безопасные для расшифровки данных, зашифрованных с режим сцепления блоков шифра (CBC), присущая симметричному шифрованию, если проверяемый заполнения был применен без гарантируя целостность зашифрованных данных, за исключением особых в других обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="611d7-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="611d7-105">Этот judgement основан на криптографических исследованиях, известные на данный момент.</span><span class="sxs-lookup"><span data-stu-id="611d7-105">This judgement is based on currently known cryptographic research.</span></span> 

## <a name="introduction"></a><span data-ttu-id="611d7-106">Вступление</span><span class="sxs-lookup"><span data-stu-id="611d7-106">Introduction</span></span>

<span data-ttu-id="611d7-107">Атака на заполнение oracle — это тип атаки зашифрованных данных, который позволяет злоумышленнику для расшифровки содержимого данных, не зная ключа.</span><span class="sxs-lookup"><span data-stu-id="611d7-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="611d7-108">Тип данных oracle относится к «тип учетной записи» которых дает злоумышленнику информацию о ли обучаться действии правильно или не.</span><span class="sxs-lookup"><span data-stu-id="611d7-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="611d7-109">Представьте себе воспроизведение на доске или карт игры с дочерним.</span><span class="sxs-lookup"><span data-stu-id="611d7-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="611d7-110">При ее лиц подсвечено будет с большой смайлик, так как она полагает, что она должна хорошо переход, который является oracle.</span><span class="sxs-lookup"><span data-stu-id="611d7-110">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="611d7-111">Как противником, можно использовать этот oracle в соответствии с планом следующего перехода.</span><span class="sxs-lookup"><span data-stu-id="611d7-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="611d7-112">Заполнение составляет определенный термин шифрования.</span><span class="sxs-lookup"><span data-stu-id="611d7-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="611d7-113">Некоторые старые шифры, которые являются алгоритмы, используемые для шифрования данных, работать на блоки данных, где каждый блок имеет фиксированный размер.</span><span class="sxs-lookup"><span data-stu-id="611d7-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="611d7-114">Если данные, которые вы хотите зашифровать не правильного размера для заполнения в блоках, данных заполняется в том случае, пока получит.</span><span class="sxs-lookup"><span data-stu-id="611d7-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="611d7-115">Многие виды заполнения требуют этого дополнения, чтобы всегда присутствовать, даже если исходная входная была подходящего размера.</span><span class="sxs-lookup"><span data-stu-id="611d7-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="611d7-116">Это позволяет дополнения, чтобы всегда безопасно удалить после расшифровки.</span><span class="sxs-lookup"><span data-stu-id="611d7-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="611d7-117">Объединения две вещи, реализации программы с oracle заполнения показывает, имеет ли расшифрованные данные допустимым заполнения.</span><span class="sxs-lookup"><span data-stu-id="611d7-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="611d7-118">Oracle может быть что-то просто возвращает значение, говорит: «Неправильному заполнению» или более сложная операция, например значительно разных время не является допустимым блоком, в отличие от недопустимый блок обработки.</span><span class="sxs-lookup"><span data-stu-id="611d7-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="611d7-119">Шифры блочным имеется еще одно свойство, — режим, который определяет связь данных в первом блоке данных во втором блоке, и так далее.</span><span class="sxs-lookup"><span data-stu-id="611d7-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="611d7-120">Одна из наиболее часто используемые режимы — CBC.</span><span class="sxs-lookup"><span data-stu-id="611d7-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="611d7-121">CBC вводит начальной случайных блок, известные как вектор инициализации (IV) и объединяет предыдущего блока с результатом статического шифрования, чтобы сделать его таким образом, шифрование и то же сообщение с тем же ключом не всегда создает такие же выходные данные зашифрованных.</span><span class="sxs-lookup"><span data-stu-id="611d7-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="611d7-122">Злоумышленник может использовать заполнение oracle, в сочетании с структуру данных CBC, для отправки сообщений слегка измененный код, который предоставляет oracle и поддерживать отправку данных, пока oracle уведомляющее правильности данных.</span><span class="sxs-lookup"><span data-stu-id="611d7-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="611d7-123">Из этого ответа злоумышленник может расшифровать сообщение байт за байтом.</span><span class="sxs-lookup"><span data-stu-id="611d7-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="611d7-124">Современные компьютерные сети являются такие высокого качества, что злоумышленник может обнаружить небольшого различия при внутреннем (менее 0,1 мс), время в удаленных системах.</span><span class="sxs-lookup"><span data-stu-id="611d7-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="611d7-125"> Приложения, которые предполагается, что успешной расшифровки может произойти только в том случае, если данные не было незаконно может быть уязвим для атак из средств, предназначенных для наблюдения за различия в успешных и неуспешных расшифровки.</span><span class="sxs-lookup"><span data-stu-id="611d7-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="611d7-126">Хотя это различие времени может быть более значимыми в некоторых языков и библиотек, чем другие, теперь считается что это практические угроз для всех языков и библиотек, когда ответ приложения сбой извлекается в учетную запись.</span><span class="sxs-lookup"><span data-stu-id="611d7-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="611d7-127">Эта атака зависит от возможности для изменения зашифрованных данных и проверьте результат с oracle.</span><span class="sxs-lookup"><span data-stu-id="611d7-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="611d7-128">Единственный способ полностью устранить атаки — обнаружение изменений к зашифрованным данным и не будет выполнять каких-либо действий с ним.</span><span class="sxs-lookup"><span data-stu-id="611d7-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="611d7-129">Стандартный способ сделать это заключается в том, для создания подписи для данных и проверки подписи, прежде, чем любые операции выполнялись.</span><span class="sxs-lookup"><span data-stu-id="611d7-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="611d7-130">Подпись должна располагаться проверяемых, не может быть создан злоумышленником, в противном случае они бы изменить зашифрованные данные, а затем вычисления новые сигнатуры на основе измененных данных.</span><span class="sxs-lookup"><span data-stu-id="611d7-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="611d7-131">Один из распространенных типов соответствующей подписью называется код проверки подлинности сообщения (HMAC).</span><span class="sxs-lookup"><span data-stu-id="611d7-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="611d7-132">Код HMAC отличается от контрольной суммы, в том, что он принимает секретный ключ, известных только пользователю, создания HMAC и проверки его пользователю.</span><span class="sxs-lookup"><span data-stu-id="611d7-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="611d7-133">Даже при отсутствии ключа не могут производить правильный HMAC.</span><span class="sxs-lookup"><span data-stu-id="611d7-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="611d7-134">При получении данных, следует воспользоваться зашифрованные данные, независимо друг от друга вычисления HMAC, с помощью секретного ключа вы отправитель общего ресурса, а затем сравнить вычисляемые HMAC, они отправлены по одному.</span><span class="sxs-lookup"><span data-stu-id="611d7-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="611d7-135">Это сравнение должно быть константном времени, в противном случае вы добавили другой выявляемых oracle, что различные типы атак.</span><span class="sxs-lookup"><span data-stu-id="611d7-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="611d7-136">Таким образом для использования дополняются блочные шифры CBC безопасно, их необходимо объединить код HMAC (или другой проверки целостности данных), можно проверить с помощью сравнения константном времени перед попыткой для расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="611d7-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="611d7-137">Так как все сообщения измененных принимать то же время сумма на выдачу отклика, атаки блокируется.</span><span class="sxs-lookup"><span data-stu-id="611d7-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="611d7-138">Кто уязвим</span><span class="sxs-lookup"><span data-stu-id="611d7-138">Who is vulnerable</span></span>

<span data-ttu-id="611d7-139">Эта уязвимость относится к управляемым и машинным приложения, которое выполняет свои собственные шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="611d7-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="611d7-140">Сюда входят, например:</span><span class="sxs-lookup"><span data-stu-id="611d7-140">This includes, for example:</span></span>

- <span data-ttu-id="611d7-141">Приложение, шифрует файл cookie для расшифровки более поздней версии на сервере.</span><span class="sxs-lookup"><span data-stu-id="611d7-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="611d7-142">Приложение базы данных, которое предоставляет пользователям для вставки данных в таблицы, столбцы которых затем расшифрованы лицом.</span><span class="sxs-lookup"><span data-stu-id="611d7-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="611d7-143">Приложение передачи данных, которое использует шифрование с помощью общего ключа для защиты передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="611d7-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="611d7-144">Приложение, которое шифрует и расшифровывает сообщения «внутри» TLS-туннеля.</span><span class="sxs-lookup"><span data-stu-id="611d7-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="611d7-145">Обратите внимание на то, что с помощью только TLS может не защищает вас в этих сценариях.</span><span class="sxs-lookup"><span data-stu-id="611d7-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="611d7-146">Уязвимого приложения:</span><span class="sxs-lookup"><span data-stu-id="611d7-146">A vulnerable application:</span></span>

- <span data-ttu-id="611d7-147">Расшифровывает данные с помощью режима шифра CBC с режимом проверяемых заполнения, например PKCS #7 или ANSI X.923.</span><span class="sxs-lookup"><span data-stu-id="611d7-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="611d7-148">Выполняет расшифровку без выполнять проверку целостности данных (через MAC или асимметричные подписи).</span><span class="sxs-lookup"><span data-stu-id="611d7-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="611d7-149">Это также применимо для приложений, построенных на основе абстракции поверх этих примитивов, таких как структура EnvelopedData Cryptographic Message Syntax (PKCS #7/CMS).</span><span class="sxs-lookup"><span data-stu-id="611d7-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="611d7-150">Связанные проблемные области</span><span class="sxs-lookup"><span data-stu-id="611d7-150">Related areas of concern</span></span>

<span data-ttu-id="611d7-151">Справочные материалы привело Майкрософт для дальнейшего было бы заботиться о CBC сообщений, которые заполняются ISO 10126-эквивалент padding, если сообщение содержит структуру хорошо известного или какого- либо нижний колонтитул.</span><span class="sxs-lookup"><span data-stu-id="611d7-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="611d7-152">Например содержимое, подготовленных в соответствии с правилами W3C XML Encryption Syntax и рекомендации по обработке (xmlenc EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="611d7-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="611d7-153">Хотя во время считалось соответствующие рекомендации консорциума W3C для подписи сообщения, а затем зашифровать, теперь рекомендуется всегда делаем шифрование then подписью.</span><span class="sxs-lookup"><span data-stu-id="611d7-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="611d7-154">Разработчики приложений должны всегда учитывать проверка применимости асимметричный ключ подписи, как отсутствует отношение доверия, присущие между асимметричного ключа и случайное сообщение.</span><span class="sxs-lookup"><span data-stu-id="611d7-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="611d7-155">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="611d7-155">Details</span></span>

<span data-ttu-id="611d7-156">Исторически сложилось так, что произошел согласие, очень важно для шифрования и проверки подлинности важные данные, с помощью средств подписи HMAC или RSA.</span><span class="sxs-lookup"><span data-stu-id="611d7-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="611d7-157">Тем не менее было меньше четкие инструкции о том, как виртуализация операции шифрования и проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="611d7-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="611d7-158">Из-за этой уязвимости, описанные в этой статье рекомендации корпорации Майкрософт — теперь всегда использовать парадигму «шифрования затем входа».</span><span class="sxs-lookup"><span data-stu-id="611d7-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="611d7-159">То есть сначала шифрование данных с помощью симметричного ключа, а затем вычислений MAC или асимметричные подписи над зашифрованного текста (зашифрованные данные).</span><span class="sxs-lookup"><span data-stu-id="611d7-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="611d7-160">При расшифровке данных, выполните обратное.</span><span class="sxs-lookup"><span data-stu-id="611d7-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="611d7-161">Во-первых Подтвердите MAC или подпись зашифрованного текста, а затем расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="611d7-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="611d7-162">Класс уязвимостей, известные как «padding атак oracle» известные существовать более 10 лет.</span><span class="sxs-lookup"><span data-stu-id="611d7-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="611d7-163">Эти уязвимости позволяют злоумышленнику расшифровать данные, зашифрованные алгоритмов симметричного блочного, таких как AES и 3DES, используя не более 4096 попыток каждого блока данных.</span><span class="sxs-lookup"><span data-stu-id="611d7-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="611d7-164">Эти уязвимости сделать использование тот факт, что блокировка шифры чаще всего используются с данными проверяемых заполнения в конце.</span><span class="sxs-lookup"><span data-stu-id="611d7-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="611d7-165">Найден, что если злоумышленник может искажать зашифрованные данные и узнать ли незаконное изменение вызвало ошибку в формате заполнения в конце, злоумышленник может расшифровать данные.</span><span class="sxs-lookup"><span data-stu-id="611d7-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="611d7-166">Изначально практические атаки были основаны на службы, которые возвращает различных кодов ошибок зависимости от того, была ли заполнение правильной, например уязвимости ASP.NET [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span><span class="sxs-lookup"><span data-stu-id="611d7-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="611d7-167">Тем не менее мы теперь уверены, что оно является удобным для проведения подобных атак, использующих только различия по синхронизации между обработки допустимых и недопустимых заполнения.</span><span class="sxs-lookup"><span data-stu-id="611d7-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="611d7-168">Условии, что схема шифрования использует подпись и проверка подписи выполняется с предопределенной среды выполнения для данной длины данных (вне зависимости от содержимого), без передачи сведений, можно проверить целостность данных Злоумышленник с помощью [канала со стороны](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="611d7-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="611d7-169">Поскольку проверки целостности отклоняет любые искаженные сообщения, устранения угроз oracle заполнения.</span><span class="sxs-lookup"><span data-stu-id="611d7-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="611d7-170">Руководство</span><span class="sxs-lookup"><span data-stu-id="611d7-170">Guidance</span></span>

<span data-ttu-id="611d7-171">В первую очередь Корпорация Майкрософт рекомендует, что любые данные, которые имеет конфиденциальность должен передаваться через слой безопасности TLS (Transport), унаследованный от него к Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="611d7-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="611d7-172">Далее следует проанализируйте приложения:</span><span class="sxs-lookup"><span data-stu-id="611d7-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="611d7-173">Понять, какие шифрования, выполнении и точно какие Шифрование обеспечивается корпорацией платформ и API, вы используете.</span><span class="sxs-lookup"><span data-stu-id="611d7-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="611d7-174">Быть уверенным, что каждый использования на каждом уровне симметричный [алгоритм шифрования блока](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), такие как AES и 3DES, в режиме CBC внедрить использование проверку целостности данных, ключом которого является секрет (асимметричные подписи, код HMAC, или чтобы изменить режим шифрования для [проверку подлинности шифрования](https://en.wikipedia.org/wiki/Authenticated_encryption) режим (AE), как GCM или CCM).</span><span class="sxs-lookup"><span data-stu-id="611d7-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="611d7-175">На основе проведенных исследований, обычно считается, если действия проверки подлинности и шифрования выполняются независимо друг от друга не AE режимов шифрования, проверки подлинности зашифрованного текста (шифрование, затем — знак) лучше всего Общие.</span><span class="sxs-lookup"><span data-stu-id="611d7-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="611d7-176">Однако не опасно правильный ответ, для шифрования и этот образ не так хороши, как Расширенный совет из профессиональных криптограф.</span><span class="sxs-lookup"><span data-stu-id="611d7-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="611d7-177">Приложения, которые не могут изменять их формат обмена сообщениями, но без проверки подлинности расшифровки CBC рекомендуется пытаться добавить Устранение угроз, таких как:</span><span class="sxs-lookup"><span data-stu-id="611d7-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="611d7-178">Расшифровка не позволяя дешифратора проверить и удалить заполнение:</span><span class="sxs-lookup"><span data-stu-id="611d7-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="611d7-179">Любое заполнение, которая была применена по-прежнему должен быть удален или игнорировать, вы перемещаете нагрузку в приложение.</span><span class="sxs-lookup"><span data-stu-id="611d7-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="611d7-180">Преимущество в том, что заполнение проверки и удаления могут быть включены в другую логику проверки данных приложения.</span><span class="sxs-lookup"><span data-stu-id="611d7-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="611d7-181">Если проверка заполнения и проверке данных может осуществляться в константном времени, сокращается угрозы.</span><span class="sxs-lookup"><span data-stu-id="611d7-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="611d7-182">Так как Интерпретация заполнение меняется длина предполагаемых сообщения, по-прежнему возможны сведения о времени, созданный на основе этого подхода.</span><span class="sxs-lookup"><span data-stu-id="611d7-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="611d7-183">Измените режим заполнения расшифровки ISO10126:</span><span class="sxs-lookup"><span data-stu-id="611d7-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="611d7-184">Заполнение расшифровки ISO10126 совместим с заполнение шифрования PKCS7 и заполнение ANSIX923 шифрования.</span><span class="sxs-lookup"><span data-stu-id="611d7-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="611d7-185">Изменение режима позволяет сократить набор знаний oracle заполнения 1 байту, а не весь блок.</span><span class="sxs-lookup"><span data-stu-id="611d7-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="611d7-186">Тем не менее если содержимое имеет известный нижний колонтитул, например закрывающего XML-элемента, связанные атак можно продолжать атаковать остальную часть сообщения.</span><span class="sxs-lookup"><span data-stu-id="611d7-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="611d7-187">Кроме того, это не означает восстановления открытого текста в ситуациях, где злоумышленник может приводить открытого текста должны шифроваться со смещением другое сообщение несколько раз.</span><span class="sxs-lookup"><span data-stu-id="611d7-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="611d7-188">Шлюз оценки ослабление сигнала о времени вызова расшифровки:</span><span class="sxs-lookup"><span data-stu-id="611d7-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="611d7-189">Вычисление времени удержания необходимо иметь как минимум, превышающий максимальный объем времени, которые могут быть выполнены операции расшифровки для любой сегмент данных, содержащий заполнения.</span><span class="sxs-lookup"><span data-stu-id="611d7-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="611d7-190">Время вычисления должны выполняться в соответствии с инструкциями в [получения отметки времени с высоким разрешением](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), не с помощью <xref:System.Environment.TickCount?displayProperty=nameWithType> (при условии наката over/переполнением) или вычитания две метки времени системы (при условии коррекции NTP ошибки).</span><span class="sxs-lookup"><span data-stu-id="611d7-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="611d7-191">Время вычислений должен быть включают в себя операции расшифровки, включая все возможные исключения в под или приложений C++, входные данные не только в конце.</span><span class="sxs-lookup"><span data-stu-id="611d7-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="611d7-192">Если было еще определено об успехе или неудаче, gate времени необходимо вернуть сбой, когда истечет срок его действия.</span><span class="sxs-lookup"><span data-stu-id="611d7-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="611d7-193">Службы, которые выполняются без проверки подлинности расшифровки должны иметь наблюдения для обнаружения, что представила «недопустимый» сообщения были переданы через.</span><span class="sxs-lookup"><span data-stu-id="611d7-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="611d7-194">Имейте в виду, что этот сигнал выполняет ложных срабатываний (законно поврежденные данные) и ложных отрицательных результатов (рассредоточения атаки через достаточно долго, чтобы избежать обнаружения).</span><span class="sxs-lookup"><span data-stu-id="611d7-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="611d7-195">Поиск уязвимого кода - собственных приложений</span><span class="sxs-lookup"><span data-stu-id="611d7-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="611d7-196">Для программ, рассчитанных криптографии Windows: Библиотека следующего поколения (CNG):</span><span class="sxs-lookup"><span data-stu-id="611d7-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="611d7-197">Вызов расшифровки [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), указав `BCRYPT_BLOCK_PADDING` флаг.</span><span class="sxs-lookup"><span data-stu-id="611d7-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="611d7-198">Дескриптор ключа инициализации, вызвав [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) с [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) присвоено `BCRYPT_CHAIN_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="611d7-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="611d7-199">Так как `BCRYPT_CHAIN_MODE_CBC` используется по умолчанию, затронутых код не может иметь назначить любое значение для `BCRYPT_CHAINING_MODE`.</span><span class="sxs-lookup"><span data-stu-id="611d7-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="611d7-200">Для программ, созданных с помощью более старых API шифрования Windows:</span><span class="sxs-lookup"><span data-stu-id="611d7-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="611d7-201">Вызов расшифровки [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) с `Final=TRUE`.</span><span class="sxs-lookup"><span data-stu-id="611d7-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="611d7-202">Дескриптор ключа инициализации, вызвав [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) с [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) присвоено `CRYPT_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="611d7-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="611d7-203">Так как `CRYPT_MODE_CBC` используется по умолчанию, затронутых код не может иметь назначить любое значение для `KP_MODE`.</span><span class="sxs-lookup"><span data-stu-id="611d7-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="611d7-204">Поиск уязвимого кода - приложений с управляемым кодом</span><span class="sxs-lookup"><span data-stu-id="611d7-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="611d7-205">Вызов расшифровки <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> или <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> методы <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="611d7-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="611d7-206">Это включает в себя следующие производных типов в .NET, но может также включать сторонние типы:</span><span class="sxs-lookup"><span data-stu-id="611d7-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="611d7-207"><xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Было установлено на <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, или <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="611d7-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="611d7-208">Так как <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> используется по умолчанию, затронутых код может никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="611d7-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="611d7-209"><xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Было установлено на <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="611d7-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="611d7-210">Так как <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> используется по умолчанию, затронутых код может никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="611d7-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="611d7-211">Поиск уязвимого кода - синтаксис криптографического сообщения</span><span class="sxs-lookup"><span data-stu-id="611d7-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="611d7-212">Сообщения CMS EnvelopedData, зашифрованное содержимое использует режим CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), (1.3.14.3.2.7) DES, 3DES (1.2.840.113549.3.7) или версии-кандидата 2 (1.2.840.113549.3.2) — уязвимости, также как и в случае сообщений с помощью любой другие алгоритмы блочного шифра в режиме CBC.</span><span class="sxs-lookup"><span data-stu-id="611d7-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="611d7-213">Хотя потоковых шифров, не подвержены влиянию этой уязвимости, корпорация Майкрософт рекомендует всегда проверки ContentEncryptionAlgorithm значения проверки подлинности данные.</span><span class="sxs-lookup"><span data-stu-id="611d7-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="611d7-214">Для управляемых приложений, EnvelopedData CMS, большой двоичный объект может быть обнаружено в любое значение, которое передается <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="611d7-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="611d7-215">Для собственных приложений, CMS EnvelopedData BLOB-объекта могут быть обнаружены как любое значение, указанное на дескриптор CMS с помощью [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) , что приводит к [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) является `CMSG_ENVELOPED` и/или дескриптор CMS позже отправляются `CMSG_CTRL_DECRYPT` инструкции с помощью [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span><span class="sxs-lookup"><span data-stu-id="611d7-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="611d7-216">Пример уязвимого кода — управляемые</span><span class="sxs-lookup"><span data-stu-id="611d7-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="611d7-217">Этот метод считывает файл cookie и расшифровывает его, и проверка целостности данных является видимым.</span><span class="sxs-lookup"><span data-stu-id="611d7-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="611d7-218">Таким образом содержимое файла cookie, который считывается с помощью данного метода могут подвергнуться атаке пользователь, получивший его или любой злоумышленник получил значение зашифрованного файла cookie.</span><span class="sxs-lookup"><span data-stu-id="611d7-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="611d7-219">Следующий пример кода, рекомендуется использовать методы — управляемые</span><span class="sxs-lookup"><span data-stu-id="611d7-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="611d7-220">В следующем примере кода используется формат нестандартных сообщений</span><span class="sxs-lookup"><span data-stu-id="611d7-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="611d7-221">где `cipher_algorithm_id` и `hmac_algorithm_id` алгоритм представляют собой локальную (нестандартным) представления этих алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="611d7-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="611d7-222">Эти идентификаторы смысл в других частях вашей существующей протокол обмена сообщениями, а не как исходного сцепленные потока данных.</span><span class="sxs-lookup"><span data-stu-id="611d7-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="611d7-223">В этом примере также использует только один главный ключ для получения ключа шифрования и ключа HMAC.</span><span class="sxs-lookup"><span data-stu-id="611d7-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="611d7-224">Оно предоставляется только в качестве удобства для включения приложения, ключом которого является отдельным элементом, в приложение с ключом двумя и поощрить, сохраняя два ключа, как разные значения.</span><span class="sxs-lookup"><span data-stu-id="611d7-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="611d7-225">Дальнейшей гарантирует, что ключ HMAC и ключ шифрования не окажутся не синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="611d7-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="611d7-226">В этом примере не принимает <xref:System.IO.Stream> для шифрования или расшифровки.</span><span class="sxs-lookup"><span data-stu-id="611d7-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="611d7-227">Текущий использует формат данных однопроходное шифрования сложным из-за `hmac_tag` значение предшествует зашифрованный текст.</span><span class="sxs-lookup"><span data-stu-id="611d7-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="611d7-228">Тем не менее этот формат был выбран, поскольку он поддерживает все элементы фиксированного размера в начале, чтобы не усложнять средство синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="611d7-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="611d7-229">Формат данных расшифровка однопроходное есть вероятность, хоть разработчик предупреждение для вызова GetHashAndReset и проверьте результат перед вызовом TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="611d7-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="611d7-230">Если важно шифрования потоковой передачи, затем в другой режим AE может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="611d7-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
