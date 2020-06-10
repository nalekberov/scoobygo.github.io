---
layout: post
lang: az
title:  "Observer Pattern"
---

**Qeyd: Dilimizin texniki leksikonu olduqca məhduddur, ona görə bəzi sizə tanış olmayan terminlər görə bilərsiniz, tövsiyyələrini mənə yaza bilərsiniz**


Adından bəlli olduğu kimi bu pattern izləmə ilə bağlıdır.

# Nədir bu pattern

Observer patterni individual üzvolan (Subscriber) obyektlərin yayımlayan (Publisher) obyetin vəziyyət dəşikliyi ilə bağlı olan hadisə axınına üzvolma mexanizmini irəli sürür. Bu patterndə *subyekt* olan obyekt, və bunu *izləyən* obyektlər - izləyəcilər olur. Subyekt özünə izləyicilərini əlavə edir, və özünün hal dəyişikliyi vaxtı izləyicilərini avtomatik olaraq xəbərdar edir. Buna başqa deyimlə Publish-Subscribe də demək olar, Subyekt Publisher, onun izləyiciləri isə Subscriberlər olur.

# Bəs hansı hallarda istifadə oluna bilər?
Təsəvvür edin E-kommersiya məhsulu üzərində işləyirsiniz, istifadəçiniz hər uğurlu alış-verişi zamanı verilənlər bazasına bu barədə qeyd yazmaq, e-mail göndərmək, bildiriş əlavə etmək və s. etmək istəyirsiniz.

# Real həyatdan nümunə
Bunu bir çoxumuzu aylıq maqazinlərə və ya qəzetlərə üzv olaraq edirik. Bu halda subyekt qəzet, bizlər isə izləyici rolunda çıxış edirik, qəzet bizi hər ay xəbərdar edir.


# Necə tətbiq olunur
Subyekt olan obyekt özünə üzv, üzvlüyü ləğv edə, və xəbərdar edə bilmək metodları, İzləyənlər isə subyektin onu xəbərdar etməsi üçün metoduna sahib olmalıdır. Bir qayda olaraq bu patterndə iştirak edən obyektlər bu patternin interfeysini tətbiq etməlidir. PHP-də bu məqsədlə *SPLObserver* və *SPLSubject*, əlbəttə bunu özünüz də yaza bilərsiniz, amma var olan həlli istifadə etmək daha məqsədəuyğundur.

Nümunə olaraq

```php

<?php

class Magazine implements  \SplSubject
{
    private $observers;
    private $name;

    public function __construct($name)
    {
        $this->name = $name;
        $this->observers = new \SplObjectStorage();
    }

    /**
     * {@inheritdoc}
     */
    public function attach(SplObserver $observer)
    {
        $this->observers->attach($observer);
    }

    /**
     * {@inheritdoc}
     */
    public function detach(SplObserver $observer)
    {
        $this->observers->detach($observer);
    }

    /**
     * {@inheritdoc}
     */
    public function notify()
    {
        /** @var SplObserver $observer */
        foreach ($this->observers as $observer) {
            $observer->update($this);
        }
    }

    public function getName()
    {
        return $this->name;
    }
}

class Subscriber1 implements SplObserver
{
    /**
     * {@inheritdoc}
     */
    public function update(SplSubject $subject)
    {
        echo sprintf("%s \"%s\" jurnalının bu aykı sayını aldı!\n", __CLASS__, $subject->getName());
    }
}

class Subscriber2 implements SplObserver
{
    /**
     * {@inheritdoc}
     */
    public function update(SplSubject $subject)
    {
        echo sprintf("%s \"%s\" jurnalının bu aykı sayını aldı!\n", __CLASS__, $subject->getName());
    }
}

$subscriber1 = new Subscriber1();
$subscriber2 = new Subscriber2();

$magazine = new Magazine('Mad Magazine');

$magazine->attach($subscriber1);
$magazine->attach($subscriber2);
$magazine->notify();

/*

Ekranda görünəcək

Subscriber1 "Mad Magazine" jurnalının bu aykı sayını aldı!
Subscriber2 "Mad Magazine" jurnalının bu aykı sayını aldı!

*/

```
