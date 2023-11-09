<script>
    import HeroImage from "../images/stylepod-lobby.jpg";
    import emailjs from "@emailjs/browser";

    let serviceID = "service_6zwy1h9";
    let templateID = "template_72q0lah";
    let publicAPIKEY = "EKhg1uI3lR4My65gj";

    function sendEmail(e) {
        emailjs.sendForm(serviceID, templateID, e.target, publicAPIKEY).then(
            (result) => {
                alert("Email sent!");
                console.log("SUCCESS!", result.text);
            },
            (error) => {
                alert("Email not sent, try again.");
                console.log("FAILED...", error.text);
            }
        );
    }
</script>

<div>
    <div class="hero">
        <h1 class="hero-text">
            Own your own business at Stylepod in Carytown.
        </h1>
        <img class="hero-image" src={HeroImage} alt="" />
    </div>
    <div class="main-content">
        <h2>About Us</h2>
        <p>
            We are a premium salon and spa suite provider located in the heart
            of CaryTown. Since 2014 we've specialized in beauty and wellness
            professionals.
        </p>
        <p>
            Whether you’re a cosmetologist, esthetician, eyelash provider, nail
            technician, or massage therapist we have a suite that may fit your
            needs.
        </p>
        <p>
            Contact us to inquire about suite rental opportunities and
            availability.
        </p>
        <h2>Who's here?</h2>
        <div class="ul-container">
            <ul>
                <li>
                    <span><b>100</b> - wigsmoke</span>
                </li>
                <li>
                    <span><b>102</b> - Rosalee Walker & Susan Prather</span>
                </li>
                <li>
                    <span><b>103</b> - Rustic Roots, LLC</span>
                </li>
                <li>
                    <span><b>104</b> - Carytown Massage</span>
                </li>
                <li>
                    <span> <b>105</b> - Lomi Integrated Massage</span>
                </li>
            </ul>
            <ul>
                <li>
                    <span> <b>107</b> - Sara Baltzegar Hair LLC</span>
                </li>
                <li>
                    <span> <b>109</b> - Available</span>
                </li>
                <li>
                    <span> <b>110</b> - Style by Karen</span>
                </li>
                <li>
                    <span> <b>111</b> - Images</span>
                </li>
                <li>
                    <span><b>112</b> - II Shea Hair Studio LLC</span>
                </li>
            </ul>
        </div>
        <h2 id="contact">Contact Us</h2>
        <p>
            Stylepod Studios is in the heart of Carytown at 3316 West Cary St,
            Richmond VA 23221. There is free parking behind our building and
            paid parking available in a nearby parking garage. You can contact
            us via the form below or reach out to our number: <a
                href="tel:+1(804)353-2300">(804) 353-2300</a
            >
        </p>

        <form on:submit|preventDefault={sendEmail}>
            <label
                >Name

                <input class="info" type="text" name="name" required /></label
            >
            <label>
                Email
                <input class="info" name="email" type="email" required />
            </label>
            <label>
                Phone Number
                <input class="info" name="phonenumber" type="tel" required />
            </label>
            <label
                >Message
                <textarea name="message" /></label
            >
            <input type="submit" value="Send" class="submit" />
        </form>
    </div>
</div>

<style lang="scss">
    @use "../node_modules/rfs/scss" as rfs;
    div.hero {
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: relative;
        height: 500px;
        background-color: black;

        h1.hero-text {
            @include rfs.margin-left(16px);
            @include rfs.margin-right(16px);
            z-index: 1;
            color: white;
        }

        img.hero-image {
            opacity: 0.75;
            position: absolute;
            top: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }

    div.main-content {
        margin-left: 0;
        margin-right: 0;
    }

    @media only screen and (min-width: 860px) {
        div.main-content {
            @include rfs.margin-left(16px);
            @include rfs.margin-right(16px);
        }
    }

    div.ul-container {
        display: flex;
        flex-direction: column;
    }
    ul {
        margin-top: 0;
        margin-bottom: 0;
        list-style: none;
        padding-left: 0;
        li {
            display: flex;
            flex-direction: row;
        }
    }

    ul:first-child {
        margin-right: 0px;
    }

    @media only screen and (min-width: 800px) {
        div.ul-container {
            display: flex;
            flex-direction: row;
        }

        ul:first-child {
            margin-right: 36px;
        }
    }
    p {
        max-width: 800px;
    }

    form {
        display: flex;
        flex-direction: column;
        width: 100%;
        max-width: 400px;
        label {
            width: 100%;
            font-weight: 700;
            display: flex;
            flex-direction: column;
            input.info {
                @include rfs.font-size(20px);
                @include rfs.margin-top(12px);
                @include rfs.margin-bottom(12px);
                width: 100%;
                border: 2px solid rgb(232, 232, 232);
                border-radius: 2px;
                font-size: 20px;
                @include rfs.font-size(20px);
                font-family: "Quattrocento Sans", sans-serif;
            }
            input:focus {
                outline: none !important;
            }
            textarea {
                width: 100%;
                height: 200px;
                border: 2px solid rgb(232, 232, 232);
                border-radius: 2px;
                font-size: 20px;
                @include rfs.font-size(20px);
                font-family: "Quattrocento Sans", sans-serif;
            }
            textarea:focus {
                outline: none !important;
            }
        }
    }
    input.submit {
        width: fit-content;
        @include rfs.margin-top(12px);
        padding: 24px;
        @include rfs.font-size(20px);
        font-family: "DM Serif Display", serif;
        background-color: rgba(233, 135, 9, 100);
        color: #f8f8ff;
        border: none;
        border-radius: 0;
        cursor: pointer;
    }

    p a {
        font-weight: 700;
        color: rgba(233, 135, 9, 100);
    }
</style>
