<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ResQFood</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <style>
        .jumbotron {
            background-image: url('https://images.app.goo.gl/c4scB5RBXfWXDaZg8');
            background-size: cover;
            color: #000000; /* Changed text color to black */
        }
        .about-content {
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 10px;
            margin-top: 20px;
            display: none; /* Hide by default */
        }
        .cards{
            border:black;
            border-radius:10px;
            padding:20px;
            margin:10px;
        }
        .each_card_item{
            padding:20px;
        }
        .map_image{
            height:350px;
            width:400px;
        }
        .reward_image{
            height:400px;
            width:700px;
            padding-left:350px;
        }
        .image-nav{
            height:60px;
            width:60px;
            padding:1px;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class=" py-3">
        <div class="container">
            <h1 class="text-center">ResQFood</h1>
        </div>
    </header>
    

    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-light bg-dark navbar-dark">
        <a class="navbar-brand" href="#">
            <img class="image-nav" src="data:image/jpeg;base64,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
            IPNAre72FINV/1b//Z"/>
        </a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
          <div class="navbar-nav ml-auto ">
            <a class="nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
            <a class="nav-link" href="#" onclick="openMapsWindow()">Maps</a>
            <a class="nav-link" href="#" onclick="showAboutContent()">About</a>
            <a class="nav-link" href="#">Contact Us</a>
            <a class="nav-link" href="#"  data-toggle="modal" data-target="#loginModal">Login/Sign Up</a>
          </div>
        </div>
    </nav>




    <div class="modal fade" id="loginModal" tabindex="-1" role="dialog" aria-labelledby="loginModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="loginModalLabel">Login/Signup</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                    <ul class="nav nav-tabs" id="loginTab" role="tablist">
                        <li class="nav-item">
                            <a class="nav-link active" id="login-tab" data-toggle="tab" href="#login" role="tab" aria-controls="login" aria-selected="true">Login</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" id="signup-tab" data-toggle="tab" href="#signup" role="tab" aria-controls="signup" aria-selected="false">Signup</a>
                        </li>
                    </ul>
                    <div class="tab-content" id="loginTabContent">
                        <div class="tab-pane fade show active" id="login" role="tabpanel" aria-labelledby="login-tab">
                            <form action="#" method="post" onsubmit="return validateLoginForm()">
                                <div class="form-group">
                                    <label for="loginEmail">Email address</label>
                                    <input type="email" class="form-control" id="loginEmail" aria-describedby="emailHelp" placeholder="Enter email">
                                </div>
                                <div class="form-group">
                                    <label for="loginPassword">Password</label>
                                    <input type="password" class="form-control" id="loginPassword" placeholder="Password">
                                </div>
                            <center><button type="submit" class="btn btn-primary">Login</button></center>
                            </form>
                        </div>
                        <div class="tab-pane fade" id="signup" role="tabpanel" aria-labelledby="signup-tab">
                            <form action="#" method="post" onsubmit="return validateSignupForm()">
                                <div class="form-group">
                                    <label for="signupEmail">Email address</label>
                                    <input type="email" class="form-control" id="signupEmail" aria-describedby="emailHelp" placeholder="Enter email">
                                </div>
                                <div class="form-group">
                                    <label for="signupPassword">Create Password</label>
                                    <input type="password" class="form-control" id="signupPassword" placeholder="Password">
                                    <label for="signupPassword">Confirm Password</label>
                                    <input type="password" class="form-control" id="signupPassword" placeholder="Password">
                                </div>
                                <center><button type="submit" class="btn btn-primary">Signup</button></center>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Jumbotron -->
    <div class="jumbotron text-center">
        <div>
            <img style="height:200px;width:230px;background-color:white;" 
            src="data:image/jpeg;base64,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
            IPNAre72FINV/1b//Z"/>
        </div>
        <br>
        <br>
        <h2>Welcome to ResQFood</h2>
        <p>Where every meal counts.</p>
        <p>Join us in our mission to end hunger.</p>
        <p>Together, we can make a difference!</p>
        <button class="btn btn-primary" onclick="display('sectionInfoAbout')">Get Involved</button>
    </div>

   
    <div id="aboutContent">
    <!-- About Content -->
        <div class="container">
            <div class="about-content" >
                <h3>About ResQFood</h3>
                <ul type="disc">
                <li>
                    ResQFood aims to provide a sustainable solution to hunger by utilizing vending machines to store and distribute surplus food to those in need.
                </li>
                <li>
                Our vending machines are strategically located in communities where access to food is limited. They are stocked with nutritious meals and snacks that have been carefully segregated to ensure quality and safety.
                </li>
                <li>
                    Through our innovative approach, we empower individuals to access food conveniently and without stigma, promoting dignity and inclusivity for all.
                </li>
                </ul>
            </div>

            <div class="card cards flex-row">
                <div>
                    <img class="each_card_item map_image" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTe1skWF-nrFJepO55y8ilUEy21qBrHyewbQUMwSdxMIY39zJtoC9ropflyHxaYD_i3Gr4&usqp=CAU"/>
                </div>
                <div class="each_card_item">
                    <h1>Maps</h1>
                    <br>
                    <p>
                        Explore nearby food options effortlessly through our Vending Machine! Discover nearby 
                        restaurants, cafes, and eateries with just a few clicks. Satisfy your cravings conveniently 
                        with our intuitive interface.
                    </p>
                </div>
            </div>

            <div class="card cards flex-row">
                <div class="each_card_item">
                    <h1>Rewards</h1>
                    <br>
                    <p>
                        Easily find nearby food with our Vending Machine! 
                        Discover eateries and contribute to reducing food waste. 
                        Earn rewards and coupons for d umping unused items.
                    </p>
                </div>
                <div>
                    <img class="reward_image each_card_item" src="https://media.istockphoto.com/id/1349342776/photo/3d-rendering-of-open-gift-box-suprise-earn-point-concept-loyalty-program-and-get-rewards.jpg?s=612x612&w=0&k=20&c=52aZTHMSNfSMnWPh6JNbpSC7EesVLwNwFH01mCDIArE="/>
                </div>
            </div>        

            <div class="card cards flex-row">
                <div>
                    <img class="each_card_item map_image" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRJ2me2zhTnwsmwvQrCLfnrFqNdFjBpuPljhaymH7o0-BLqQs82jTjNtyR-gtox41n8MxQ&usqp=CAU"/>
                </div>
                <div class="each_card_item">
                    <h1>Volunteer Oppurtunity</h1>
                    <br>
                    <p>
                        Join us in updating information and food details! Volunteers needed to keep our project accurate and informative. 
                        Make an impact, learn, and connect with like-minded individuals. Interested? Contact us at <a href="#">ResQFood@gmail.com</a>,Ph.No:91+xxxxxx Together, let's make a difference!
                        This concise note should capture the essence of the volunteer opportunity while providing a clear call to action for 
                        interested individuals to get in touch. 
                    </p>
                    <a href="file:///C:/Users/adars/Downloads/login_validation.html">Join Us</a>
                </div>
            </div>

            <div class="card cards flex-row">
                <div class="each_card_item">
                    <h1>About Us</h1>
                    <br>
                    <p>
                        Our vending machine initiative tackles hunger head-on by providing round-the-clock access to nutritious food. Through strategic placement and partnerships, 
                        we ensure that no one goes without a meal. With community involvement and technological innovation, we're making a tangible difference in the fight against food insecurity.
                        This version maintains brevity while conveying the essential information about your vending machine project and its mission to combat hunger.
                    </p>
                </div>
                <div>
                    <img class="reward_image each_card_item" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRS5wDypGmHShFzfNhsoGaufe1MeyepUxRcDLtO2xDq4velLCY0lf4aKH72E_iNCnZtm0M&usqp=CAU"/>
                </div>
            </div>       
            <div class="card cards flex-row">
                <div>
                    <img class="each_card_item map_image" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRs3IVkuRMpBO0a715QljNuEl5-BWfxjPCIYDP6wrbYMw3aQfRdGkYccxZ4aH8dISvnaQY&usqp=CAU"/>
                </div>
                <div class="each_card_item">
                    <h1>Key Points</h1>
                    <br>
                    <ul>
                        <li>Accessibility in various locations</li>
                        <li>Continues availability</li>
                        <li>Diverse and nutritious options</li>
                        <li>Quick and convinient service</li>
                        <li>'Food Waste' Reduction</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <!-- Login Modal -->
    <div class="modal fade" id="loginModal" tabindex="-1" role="dialog" aria-labelledby="loginModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
            <!-- Modal content goes here -->
        </div>
    </div>

    <!-- JavaScript for Form Validation and About Content -->
    <script>
        function validateLoginForm() {
            // Your login form validation logic goes here
        }

        function validateSignupForm() {
            // Your signup form validation logic goes here
        }

        function openMapsWindow() {
            // Open Google Maps or any other maps application
            window.open("https://maps.google.com", "_blank");
        }

        function showAboutContent() {
            // Show the about content when the "About" menu is clicked
            var aboutContent = document.getElementById("aboutContent");
            if (aboutContent.style.display === "none") {
                aboutContent.style.display = "block";
            } else {
                aboutContent.style.display = "none";
            }
        }
    </script>
</body>
</html>
