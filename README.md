# IT-eBooks API PHP SDK
A simple class for interacting with IT-eBooks API with PHP

- Requires cURL
- TODO figure out the minimum version PHP

# To use:
`<?php
require "class.itebooks.php";

$ite_client = new ItEbooksApi();

$json = $ite_client->search('php');

var_dump($json);

/*
{
    "Error": "0",
    "Time": 0.0108,
    "Total": "149",
    "Page": 1,
    "Books": [
        {
            "ID": 3426521078,
            "Title": "PHP: The Good Parts",
            "SubTitle": "Delivering the Best of PHP",
            "Description": "Get past all the hype about PHP and dig into the real power of the language. This book explores the most useful features of PHP and how they can speed up the web development process, and explains why the most commonly used PHP elements are often misu ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/3\/php_the_good_parts.jpg",
            "isbn": "9780596804374"
        },
        {
            "ID": 427318464,
            "Title": "Pro PHP Application Performance",
            "SubTitle": "Tuning PHP Web Projects for Maximum Performance",
            "Description": "This book contains tips, tricks, and techniques to make new and existing PHP applications much faster and less resource-hungry.\n\nPro PHP Application Performance will help you understand all the technologies and components which play a role in how w ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/6\/pro_php_application_performance.jpg",
            "isbn": "9781430228981"
        },
        {
            "ID": 1167030458,
            "Title": "Node.js for PHP Developers",
            "SubTitle": "Porting PHP to Node.js",
            "Description": "If you're an experienced PHP developer, you already have a head start on learning how to write Node.js code. In this book, author Daniel Howard demonstrates the remarkable similarities between the two languages, and shows you how to port your entire ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/3\/node.js_for_php_developers.jpg",
            "isbn": "9781449333607"
        },
        {
            "ID": 1135257952,
            "Title": "The PHP Anthology, Volume 1",
            "SubTitle": "Object Oriented PHP Solutions",
            "Description": "A compilation of best practice solutions to common Web Development problems in PHP, focusing on the achievement of practical goals by applying well-structured, object orientated software design principles.\n\nIn addition to being an excellent referen ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/7\/the_php_anthology_volume_1.jpg",
            "isbn": "9780957921856"
        },
        {
            "ID": 1965363337,
            "Title": "The PHP Anthology, Volume 2",
            "SubTitle": "Object Oriented PHP Solutions",
            "Description": "A compilation of best practice solutions to common Web Development problems in PHP, focusing on the achievement of practical goals by applying well-structured, object orientated software design principles.\n\nVolume 2 covers the applications of PHP i ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/7\/the_php_anthology_volume_2.jpg",
            "isbn": "9780957921849"
        },
        {
            "ID": 2118623082,
            "Title": "Plug-In PHP: 100 Power Solutions",
            "SubTitle": "Simple Solutions to Practical PHP Problems",
            "Description": "This practical guide gives you 100 ready-to-run PHP functions for solving most of the main problems you encounter when building a dynamic website with PHP. Every plug-in in the book offers a complete and working solution for a result you can achieve ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/13\/plug-in_php_100_power_solutions.jpg",
            "isbn": "9780071666596"
        },
        {
            "ID": 4171804729,
            "Title": "CodeIgniter for Rapid PHP Application Development",
            "SubTitle": "Improve your PHP coding productivity with the free compact open-source MVC CodeIgniter framework!",
            "Description": "CodeIgniter (CI) is a powerful open-source PHP framework with a very small footprint, built for PHP coders who need a simple and elegant toolkit to create full-featured web applications. CodeIgniter is an MVC framework, similar in some ways to the Ra ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/14\/codeigniter_for_rapid_php_application_development.jpg",
            "isbn": "9781847191748"
        },
        {
            "ID": 590620357,
            "Title": "PHP 5 E-commerce Development",
            "SubTitle": "Create a flexible framework in PHP for a powerful e-commerce solution",
            "Description": "The popularity of online shopping has increased dramatically over the past few years. There are plenty of options available if you not are planning to build your own e-commerce solution but sometimes it's better to use your own solutions. It may be e ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/14\/php_5_e-commerce_development.jpg",
            "isbn": "9781847199645"
        },
        {
            "ID": 3896293091,
            "Title": "Instant Simple Botting with PHP",
            "SubTitle": "Enhance your botting skills and create your own web bots with PHP",
            "Description": "Bots can be used effortlessly to execute projects and tasks that will save time and funds. Bots are powerful tools that should be in every knowledgeable programmer's toolbox. Developing and integrating bots into your programs may be easier than expec ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/14\/instant_simple_botting_with_php.jpg",
            "isbn": "9781782169291"
        },
        {
            "ID": 3791959216,
            "Title": "PHP Cookbook, 3rd Edition",
            "SubTitle": "Solutions & Examples for PHP Programmers",
            "Description": "Want to understand a certain PHP programming technique? Or learn how to accomplish a particular task? This cookbook is the first place to look. With more than 350 code-rich recipes revised for PHP 5.4 and 5.5, this third edition provides updated solu ...",
            "Image": "http:\/\/s.it-ebooks-api.info\/3\/php_cookbook_3rd_edition.jpg",
            "isbn": "9781449363758"
        }
    ]
}
*/



$data = json_decode($json, true);
$bookId = $data['Books'][0]['ID'];
echo $bookId;
/*
3426521078
*/

$detailsJson = $ite_client->details($bookId);

/*
{
    "Error": "0",
    "Time": 0.00138,
    "ID": 3426521078,
    "Title": "PHP: The Good Parts",
    "SubTitle": "Delivering the Best of PHP",
    "Description": "Get past all the hype about PHP and dig into the real power of the language. This book explores the most useful features of PHP and how they can speed up the web development process, and explains why the most commonly used PHP elements are often misused or misapplied. You'll learn which parts add strength to object-oriented programming, and how to use certain features to integrate your application with databases.",
    "Author": "Peter MacIntyre",
    "ISBN": "9780596804374",
    "Year": "2010",
    "Page": "176",
    "Publisher": "O'Reilly Media",
    "Image": "http:\/\/s.it-ebooks-api.info\/3\/php_the_good_parts.jpg",
    "Download": "http:\/\/filepi.com\/i\/lllThS8"
}
*/
`

# Known Issues
- The search functionality for multiple pages is not working 100%, though it seems to work fine for a single page
- The responses come back as arrays of objects if querying for multiple pages, which is sort of inconvenient.