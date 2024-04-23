<p align="center">
  <a href="https://ee.azqaq.top"><img src="https://www.eggyparty.com/pc/gw/20230630105841/img/logo_0604c8de.png" width="150" height="56" alt="EatEggy"></a>
</p>

<div align="center">

# EatEggy

_ Web Game _

</div>


## Introduction
A web game: EatEggy

[Eggy Party Offical Twitter](https://twitter.com/eggypartyglobal)
|
[Original author's repo](https://github.com/arcxingye/EatKano)
|
[Eggy Party Offical Website](https://www.eggyparty.com/)
|
[Github Pages](https://ee.azqaq.top)

## Features

A simple ranking list(day/week/month) is provided.

You can delete all the sql/php files if you don't need them.

## Requirements
+ MySQL 5+
+ PHP 5+

## Usage

Note: if you just want to play it, go to [online version](https://ee.azqaq.top). Here is how to create your own version.

### Github Pages

You can run it on Github Pages if you don't need the ranking list.

Follow these steps to change the text displayed to what you want.

1. **Fork this repository. DON'T CHANGE DIRECTLY IN THIS PROJECT.**

2. **Open the repo you forked.** Go to `static/i18n/en.json` and find these texts below

   ```json
   {
     "game-title": "Eat Kano",
     "game-intro1": "Start from the bottom",
     "game-intro2": "Can you tap 150 times?",
     "text-level-1": "Try again?",
     "text-level-2": "Not bad",
     "text-level-3": "Nice",
     "text-level-4": "Awesome",
     "text-level-5": "R U kidding?"
   }
   ```

   You can change the text on the right side. **Note that don't remove quotes(i.e. `"`)**

3. Go to directory `static/image`. The image shown before clicking is `ClickBefore.png`, and after is `ClickAfter.png`.

   **The file type must be `png`**

4. Go to directory `static/music`. The sound played when tapping is `tap.mp3`, when ending without errors is `end.mp3`, while ending with errors is `err.mp3`.

   **The file type must be `mp3`**

5. After changing all resources to your own, go to repository `Settings` -> `Pages` -> `Source`, choose `main` branch and click `Save`.

### Deploying to Server

Follow these few steps to configure the database for ranking list on your server.

1. Create your own database and execute the script provided(e.g. use `kano` as database name).
   
   ```sql
   CREATE DATABASE kano DEFAULT CHARSET=utf8;
   USE kano;
   SOURCE kano.sql;
   ```
   
2. Change the code in `conn.php`, which contains your database info, and its content is here.

   ```php
   <?php
   // Change this to your own configuration
   $link = new mysqli('localhost','NAME','PASSWORD','kano');
   mysqli_set_charset($link, 'utf8');
   if ($link->connect_error) {
       die("Failed to connect: " . $conn->connect_error);
   }
   $ranking = "kano_rank";
   ```

   


## Others

Please star us~

Welcome to pull request!
