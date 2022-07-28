# access control

## access control

Access control is the restriction of access to an object depending on the subject. 

## what

A subject is the thing that is doing the accessing during access control.
An object is the thing being accessed during access control.

## what do we want to make sure of

### basics

Access control may require one or more of identification, authentication or authorization.
Identification is claiming of some sort of identity.
^e.g. entering & checking a username, though see expansion below
Authentication is verifying of an identification by one or more authentication factors.
^e.g. entering & checking a password.
Authorization is specifying access rights/priviledges

### identification

#### differentiation

Identification can be split into arbitrary identification and personal identification.
Arbitrary identification (my term) is claiming one corresponds to some arbitrary, pre-created entity.
^such as a suer account
Personal identification (my term) is claiming one has certain attributes (an address, citizenship, being a human).

#### identity verification

##### basics

Identity verification is ascertaining the truth of personal identification.

##### human verification

###### basics

Human verification is identity verification that one is in fact a human.
Human verification needs to be designed such that computers cannot pass it, but can grade it.

###### captcha

CAPTCHA is the human verfication process "completely automated public turing test (to tell) computers (and) humans apart"

####### ReCAPTCHA

ReCAPTCHA is the CAPTCHA implementation bought by google.

######## v1 

ReCAPTCHA v1 was based on OCR.
ReCAPTCHA v1 had two groups of words: known words and unknown words.
ReCAPTCHA v1 would show users one known word and one unknown word.
ReCAPTCHA v1 would consider the captcha solved if the known word was correct, and the unknown word got a vote of confidence for the value entered for it.
In ReCAPTCHA v1, eventually an unknown word would be added as a known word, or discarded if too uncertain.

######## v2 & v3

ReCAPTCHA v2 displays only a single checkbox, and uses behavioral analysis to check the risk of a bot. If high risk, an image captcha is displayed.
ReCAPTCHA v3 displays nothing at all, and uses behavioral analysis to return the chance of someone being human on a scale from 0 (bot) to 1 (human), allowing web administrators to take further action.

### authentication

#### basics

An authentification factor is some pre-agreed attribute of the subject used in authentification.

#### amount of authentication factors

Single/Two/Three/.../Multi-factor authentication⎵wide⎵ is using 1/2/3/.../multiple authentication factors for authentication.
SFA/2FA/3FA/.../MFA =short for=> Single/Two/Three/.../Multi-factor authentication⎵wide⎵

#### type of authentication factor

##### mapping

A type 1 authentication factor is something you know.
^e.g. password, security question
A type 2 authentication factor is something you have.
^e.g. smart cards, OTP
A type 3 authentication factor is something you are/do. 
^e.g. biometrics
knowledge/ownership/inherence factor = type 1/2/3 authentication factor.

##### type 1

Knowledge-based authentication (KBA) =syndef= type 1 authentification factor
Static/dynamic KBA is a type 1 authentication factor that is static and unchanging/derived in the moment from other data.
Shared secret =syndef= static KBA

##### type 3

A physical/behavioral biometric is a type 3 authentication factor where it is what one is/does.

#### related things

##### challenge-response authentication

Challenge-response authentication is an additional step sometimes used in authentication where the subject is sent a challenge and is expected to provide a response.
In challenge-response authentication, the challenge is some data, and the response is expected to be a unique response every time.
Challenge-response authentication is a defense against replay attacks.