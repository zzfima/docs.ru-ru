---
title: Пользовательские обновления потоков
ms.date: 03/30/2017
ms.assetid: e3da85c8-57f3-4e32-a4cb-50123f30fea6
ms.openlocfilehash: cd8385194e1f24d246e6fc398462b45bacbe15d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127365"
---
# <a name="custom-stream-upgrades"></a>Пользовательские обновления потоков
Ориентированные на потоки виды транспорта, например TCP и именованные каналы, работают с непрерывным потоком данных, установленным между клиентом и сервером. Поток реализуется объектом <xref:System.IO.Stream>. при обновлении потока клиенту требуется добавить дополнительный уровень протокола в стек каналов и он отправляет соответствующий запрос другому участнику коммуникационного канала. Обновление канала предполагает замену исходного объекта <xref:System.IO.Stream> на обновленный.  
  
 Например, можно создать поток сжатия непосредственно поверх транспортного потока. В этом случае исходный транспортный поток <xref:System.IO.Stream> заменяется потоком, который выступает в роли оболочки потока <xref:System.IO.Stream> сжатия вокруг исходного потока.  
  
 Можно применить несколько обновлений потоков, каждое из которых будет служить оболочкой для предыдущего.  
  
## <a name="how-stream-upgrades-work"></a>Принципы работы обновления потока  
 Имеется четыре компонента процесса обновления потока.  
  
1.  Обновления потока *инициатора* начинает процесс: во время выполнения она может инициировать запрос на обновление транспортного уровня канала к другой стороне связи.  
  
2.  Обновления потока *Акцептор* выполняет обновление: во время выполнения он получает запрос об обновлении от другого компьютера и по возможности принимает обновление.  
  
3.  Обновление *поставщика* создает *инициатора* на стороне клиента и *Акцептор* на сервере.  
  
4.  Обновления потока *элемента привязки* добавляется в привязки службы и клиента, а также создает поставщик во время выполнения.  
  
 Обратите внимание, что в случае нескольких обновлений инициатор и акцептор инкапсулируют конечные автоматы для определения переходов обновления, которые являются допустимыми для каждой инициации.  
  
## <a name="how-to-implement-a-stream-upgrade"></a>Реализация обновления потока  
 Windows Communication Foundation (WCF) предоставляет четыре `abstract` классы, которые можно реализовать:  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeInitiator?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeProvider?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement?displayProperty=nameWithType>  
  
 Чтобы реализовать пользовательское обновление потока, выполните следующие действия. Ниже приведена процедура минимального обновления потока на клиентском и сервером компьютерах.  
  
1.  Создайте класс, реализующий <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>.  
  
    1.  Переопределите метод <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A>, чтобы он принимал обновляемый поток и возвращал обновленный поток. Этот метод работает синхронно; имеются аналогичные методы для асинхронной инициации обновления.  
  
    2.  Переопределите метод <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A>, чтобы он проверял на необходимость дополнительных обновлений.  
  
2.  Создайте класс, реализующий <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>.  
  
    1.  Переопределите метод <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A>, чтобы он принимал обновляемый поток и возвращал обновленный поток. Этот метод работает синхронно; имеются аналогичные методы для асинхронного принятия обновления.  
  
    2.  Переопределите метод <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>, чтобы он проверял, поддерживается ли запрошенное обновление текущим акцептором обновления в данной точке процесса обновления.  
  
3.  Создайте класс, реализующий <xref:System.ServiceModel.Channels.StreamUpgradeProvider>. Переопределите методы <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> и <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A>, чтобы они возвращали экземпляры акцептора и инициатора, определенные на шагах 2 и 1.  
  
4.  Создайте класс, реализующий <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>.  
  
    1.  Переопределите метод <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> клиента и метод <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> службы.  
  
    2.  Переопределите метод <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> клиента и метод <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> службы, чтобы добавлять в свойство <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A> элемент привязки обновления.  
  
5.  Добавьте новый элемент привязки обновления потока в привязки на клиентском и серверном компьютерах.  
  
## <a name="security-upgrades"></a>Обновления системы безопасности  
 Добавление обновления системы безопасности представляет собой специальную версию общего процесса обновления потока.  
  
 WCF уже содержит два элемента привязки для обновления безопасности потока. Конфигурация безопасности транспортного уровня инкапсулируется в элементах <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> и <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>, которые можно настроить и добавить в пользовательскую привязку. Эти элементы привязки расширяют класс <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>, создающий поставщики обновления потока клиента и сервера. У этих элементов привязки имеются методы, создающие специальные классы поставщиков обновления системы безопасности потоков, которые не являются `public`, поэтому в этих двух случаях достаточно просто добавить элемент привязки в привязку.  
  
 Для сценариев обеспечения безопасности, не реализуемых с помощью описанных выше двух элементов привязки, от вышеупомянутых базовых классов инициатора, акцептора и поставщика наследуются три класса `abstract`, связанных с обеспечением безопасности:  
  
1.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator?displayProperty=nameWithType>  
  
2.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor?displayProperty=nameWithType>  
  
3.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider?displayProperty=nameWithType>  
  
 Процесс реализации обновления безопасности потока такой же, как и раньше, лишь с тем отличием, что наследование выполняется от этих трех классов. Переопределите дополнительные свойства в этих классах, чтобы предоставить среде выполнения сведения о безопасности.  
  
## <a name="multiple-upgrades"></a>Несколько обновлений  
 Чтобы создать дополнительные запросы на обновление, повторите описанный выше процесс: создайте дополнительные расширения поставщика <xref:System.ServiceModel.Channels.StreamUpgradeProvider> и элементы привязки. Добавьте в привязку элементы привязки. Дополнительные элементы привязки обрабатываться последовательно, начиная с первого элемента привязки, добавленного в привязку. В методах <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> и <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> каждый поставщик обновления может определять, как расположить себя относительно существующих параметров привязки обновления. В этом случае он должен заменить существующий параметр привязки обновления на новый составной параметр привязки обновления.  
  
 Кроме того, один поставщик обновления может поддерживать несколько обновлений. Например, может потребоваться реализовать пользовательский поставщик обновления потока, который поддерживает как безопасность, так и сжатие. Выполните следующие действия.  
  
1.  На основе класса <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> создайте класс поставщика, который создает инициатор и акцептор.  
  
2.  Создайте подкласс <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>, переопределив метод <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A>, чтобы он возвращал типы содержимого для потока сжатия и потока защиты в нужном порядке.  
  
3.  Создайте подкласс <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>, метод <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> которого может распознавать пользовательские типы содержимого.  
  
4.  Поток будет обновляться после каждого вызова методов <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> и <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>
- <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>
- <xref:System.ServiceModel.Channels.StreamUpgradeProvider>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider>
- <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
