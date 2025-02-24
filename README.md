# CampusNavigator
Campus Navigator(Lecture hall finder)


I need to design this screen using swift language on Xcode 
ChatGPT said:
To design this login screen using Swift and SwiftUI in Xcode, follow these steps:

Steps to Implement:
Create a new SwiftUI View: Open your Xcode project and create a new SwiftUI View file (e.g., LoginView.swift).
Use VStack for vertical arrangement: The elements should be arranged in a vertical stack.
Use TextField and SecureField for email and password inputs.
Add a "Forgot Password?" button below the password field.
Use Button for the "Log In" and social media login buttons.
Use Divider to separate the login options.
Style the buttons and text elements using frame, padding, background, and cornerRadius.
SwiftUI Code for Login Screen
import SwiftUI

struct LoginView: View {
    @State private var email: String = ""
    @State private var password: String = ""
    
    var body: some View {
        VStack(spacing: 20) {
            Text("Welcome !")
                .font(.title)
                .fontWeight(.bold)
            
            // Email Input
            VStack(alignment: .leading, spacing: 5) {
                Text("Email")
                    .font(.caption)
                TextField("Enter your email", text: $email)
                    .padding()
                    .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
            }
            .padding(.horizontal)
            
            // Password Input
            VStack(alignment: .leading, spacing: 5) {
                Text("Password")
                    .font(.caption)
                HStack {
                    SecureField("********", text: $password)
                    Image(systemName: "eye.slash")
                        .foregroundColor(.gray)
                }
                .padding()
                .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
            }
            .padding(.horizontal)
            
            // Forgot Password
            HStack {
                Spacer()
                Button(action: {}) {
                    Text("Forgot Password?")
                        .font(.caption)
                        .foregroundColor(.gray)
                }
            }
            .padding(.horizontal)
            
            // Login Button
            Button(action: {}) {
                Text("Log In")
                    .font(.headline)
                    .foregroundColor(.white)
                    .frame(maxWidth: .infinity)
                    .padding()
                    .background(Color.blue)
                    .cornerRadius(10)
            }
            .padding(.horizontal)
            
            // Divider with "Or"
            HStack {
                Rectangle()
                    .frame(height: 1)
                    .foregroundColor(.gray)
                Text("Or")
                    .font(.caption)
                    .foregroundColor(.gray)
                Rectangle()
                    .frame(height: 1)
                    .foregroundColor(.gray)
            }
            .padding(.horizontal)
            
            // Social Media Buttons
            VStack(spacing: 10) {
                SocialLoginButton(icon: "applelogo", text: "Continue with Apple")
                SocialLoginButton(icon: "globe", text: "Continue with Google")
                SocialLoginButton(icon: "facebook", text: "Continue with Facebook")
            }
            
            // Signup Prompt
            HStack {
                Text("Don’t have an account?")
                    .foregroundColor(.gray)
                Button(action: {}) {
                    Text("Sign up")
                        .fontWeight(.bold)
                        .foregroundColor(.blue)
                }
            }
            .padding(.top, 10)
        }
        .padding()
    }
}

// Custom Button for Social Login
struct SocialLoginButton: View {
    let icon: String
    let text: String
    
    var body: some View {
        Button(action: {}) {
            HStack {
                Image(systemName: icon)
                Text(text)
            }
            .foregroundColor(.black)
            .frame(maxWidth: .infinity)
            .padding()
            .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
        }
        .padding(.horizontal)
    }
}

// Preview
struct LoginView_Previews: PreviewProvider {
    static var previews: some View {
        LoginView()
    }
}
Key Features Implemented:
✅ TextFields for Email and Password
✅ "Forgot Password" Button
✅ Login Button with Background Color
✅ Social Login Buttons (Apple, Google, Facebook)
✅ Divider with "Or" Text
✅ Signup Prompt at Bottom

This code will replicate the UI layout in your image using SwiftUI. Let me know if you need modifications! 🚀







You said:
I'm getting this error

== DATE:

    Monday, 24 February 2025 at 18:32:05 India Standard Time
    
    2025-02-24T13:02:05Z



== PREVIEW UPDATE ERROR:

    SchemeBuildError: Failed to build the scheme “Campus_Navigator”
    
    cannot find 'ContentView' in scope
    
    Compile Campus_NavigatorApp.swift (arm64):
    /Users/sachithra010/dev/TheSequareGame/Campus Navigator/Campus_Navigator/Campus_Navigator/Campus_NavigatorApp.swift:14:13: error: cannot find 'ContentView' in scope
                ContentView()
                ^~~~~~~~~~~
    



== VERSION INFO:

    Tools: 16C5032a
    OS:    24C101
    PID:   451
    Model: iMac
    Arch:  arm64e



== ENVIRONMENT:

    openFiles = [
        /Users/sachithra010/dev/TheSequareGame/Campus Navigator/Campus_Navigator/Campus_Navigator/ContentView.swift
    ]
    wantsNewBuildSystem = true
    newBuildSystemAvailable = true
    activeScheme = Campus_Navigator
    activeRunDestination = iPhone 16 Pro variant iphonesimulator arm64
    workspaceArena = [x]
    buildArena = [x]
    buildableEntries = [
        Campus_Navigator.app
    ]
    runMode = JIT Executor



== SELECTED RUN DESTINATION:

    Simulator - iOS 18.2 | iphonesimulator | arm64 | iPhone 16 Pro | no proxy



== EXECUTION MODE OVERRIDES:

    Workspace JIT mode user setting: true
    Falling back to Dynamic Replacement: false



== PACKAGE RESOLUTION ERRORS:

    



== REFERENCED SOURCE PACKAGES:

    



== JIT LINKAGE:

    Run Destination: 78B60766-41E2-442E-AD78-1737ECAA015B-iphonesimulator18.2-arm64-iphonesimulator
    JIT Link Description {
        3:Campus_Navigator.app
    }
    



== SESSION GROUP 3072:

    workspace identifier: WorkspaceIdentifier(identifier: 87C50F62-ADEB-454B-9540-9CDE6ACD0D03)
    providers: [
        Preview Provider | LoginView_Previews provider #1 in ContentView.swift [Editor(2854)]
    ]
    translation units: [
        /Users/sachithra010/dev/TheSequareGame/Campus Navigator/Campus_Navigator/Campus_Navigator/ContentView.swift
    ]
    attributes: [
        Editor(2854):     
            isAppPreviewEnabled: false
            destinationMode: automatic
            previewSettings: [
                Registry-ContentView.swift#1[preview]:     isEnabled: false
                    boxedCanvasControlStates: []
            ]
    ]
    session: 3073
    request sessions: [
        LoginView_Previews provider #1 in ContentView.swift: not completed
    ]



== UPDATE SESSION 3073:

    Start Date: Monday, 24 February 2025 at 18:31:44 India Standard Time
    Timing {
        Elapsed Time: 0.18539798259735107s
        c9a2dc0722818502,762094904.125075,0.18539798259735107s,,PreviewUpdateSession,id:3073
        682f7dde0ad7a957,762094904.155394,0.0002599954605102539s,,MakeBuildGraph,
        e7e1b72a6c4020cd,762094904.156964,0.15317010879516602s,,WorkspaceBuild,
    }
    Preview Provider {
        UpdaterStore {
            updaterLimit: single
            expectedAbandonedIdentifiers: [2922, 2987]
        }
        Simulator {
            platform: iphonesimulator
            device: 299A7344-69FD-4886-884D-5106A91388F0 iPhone 16 Pro
            buildNumber: 22C150
            runtimePath: /Library/Developer/CoreSimulator/Volumes/iOS_22C150/Library/Developer/CoreSimulator/Profiles/Runtimes/iOS 18.2.simruntime
        }
    }
    Build Graph {
        Campus_Navigator.app (#3)
           sourceFile(file:///Users/sachithra010/dev/TheSequareGame/Campus%20Navigator/Campus_Navigator/Campus_Navigator/ContentView.swift -> ContentView.swift) (#1)
           ContentView.swift (#2)
    }
    Update Plan {
        iOS [arm64 iphonesimulator18.2 iphonesimulator] (iPhone 16 Pro, 78B60766-41E2-442E-AD78-1737ECAA015B-iphonesimulator18.2-arm64-iphonesimulator), [], thinning disabled, thunking enabled) {
            Destination: iPhone 16 Pro 78B60766-41E2-442E-AD78-1737ECAA015B | default device for iphonesimulator [
                Campus_Navigator app - Previews {
                    execution point packs [
                        [source: ContentView.swift, role: Previews] (in Campus_Navigator)
                    ]
                    translation units [
                        ContentView.swift (in Campus_Navigator.app)
                    ]
                    modules [
                        Campus_Navigator.app
                    ]
                    jit link description [
                        Campus_Navigator.app
                    ]
                }
            ]
        }
    }



== POWER STATE LOGS:

    2025-2-24, 18:29 Received power source state: Externally Powered
    2025-2-24, 18:29 No device power state user override user default value.Current power state: Full Power

ChatGPT said:
The error "cannot find 'ContentView' in scope" means that Xcode is looking for ContentView() but cannot find its definition. Here are the steps to fix it:

Fix 1: Ensure ContentView.swift Exists
In the Project Navigator (left panel in Xcode), look for ContentView.swift.
If ContentView.swift is missing, create a new SwiftUI View:
Go to File → New → File...
Select SwiftUI View → Name it ContentView.swift.
Replace the default code with:
import SwiftUI

struct ContentView: View {
    var body: some View {
        LoginView() // Replace with your login screen view
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
Fix 2: Check Campus_NavigatorApp.swift
Your Campus_NavigatorApp.swift should correctly reference ContentView().

Open Campus_NavigatorApp.swift (inside Campus_Navigator folder).
Ensure it has the following code:
import SwiftUI

@main
struct Campus_NavigatorApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView() // Make sure this exists
        }
    }
}
Fix 3: Check File Target Membership
Select ContentView.swift in Xcode.
In the File Inspector (right panel), under "Target Membership", ensure that Campus_Navigator is checked.
Fix 4: Clean and Rebuild the Project
Shortcut: Press Shift + Command + K (Clean Build Folder).
Rebuild: Press Command + B.
Fix 5: Restart Xcode and Simulator
Quit Xcode (Command + Q).
Restart Xcode and open your project.
Reset Simulator:
Open Simulator → Device → Erase All Content and Settings.
After applying these fixes, try running the project again. Let me know if you still face issues! 🚀







You said:
I need full code with these fixes and screen design

2/2

ChatGPT said:
Sure! Below is the full SwiftUI code for your login screen, along with the necessary fixes for Campus_NavigatorApp.swift and ContentView.swift.

Final Project Structure
Campus_Navigator
│── Campus_NavigatorApp.swift
│── ContentView.swift
│── LoginView.swift
1️⃣ Campus_NavigatorApp.swift (Main Entry Point)
This file ensures that ContentView is the root view of your app.

import SwiftUI

@main
struct Campus_NavigatorApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView() // Loads ContentView.swift
        }
    }
}
2️⃣ ContentView.swift (Main View)
This acts as the container for your LoginView.

import SwiftUI

struct ContentView: View {
    var body: some View {
        LoginView() // Displays the login screen
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
3️⃣ LoginView.swift (Your Login Screen UI)
This file contains the design for your login screen.

import SwiftUI

struct LoginView: View {
    @State private var email: String = ""
    @State private var password: String = ""

    var body: some View {
        VStack(spacing: 20) {
            // Title
            Text("Welcome !")
                .font(.title)
                .fontWeight(.bold)
                .padding(.top, 40)

            // Email Input
            VStack(alignment: .leading, spacing: 5) {
                Text("Email")
                    .font(.caption)
                TextField("Enter your email", text: $email)
                    .padding()
                    .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
            }
            .padding(.horizontal)

            // Password Input
            VStack(alignment: .leading, spacing: 5) {
                Text("Password")
                    .font(.caption)
                HStack {
                    SecureField("********", text: $password)
                    Image(systemName: "eye.slash") // Eye icon for visibility toggle
                        .foregroundColor(.gray)
                }
                .padding()
                .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
            }
            .padding(.horizontal)

            // Forgot Password Button
            HStack {
                Spacer()
                Button(action: {}) {
                    Text("Forgot Password?")
                        .font(.caption)
                        .foregroundColor(.gray)
                }
            }
            .padding(.horizontal)

            // Login Button
            Button(action: {}) {
                Text("Log In")
                    .font(.headline)
                    .foregroundColor(.white)
                    .frame(maxWidth: .infinity)
                    .padding()
                    .background(Color.blue)
                    .cornerRadius(10)
            }
            .padding(.horizontal)

            // OR Divider
            HStack {
                Rectangle().frame(height: 1).foregroundColor(.gray)
                Text("Or")
                    .font(.caption)
                    .foregroundColor(.gray)
                Rectangle().frame(height: 1).foregroundColor(.gray)
            }
            .padding(.horizontal)

            // Social Login Buttons
            VStack(spacing: 10) {
                SocialLoginButton(icon: "applelogo", text: "Continue with Apple")
                SocialLoginButton(icon: "globe", text: "Continue with Google")
                SocialLoginButton(icon: "facebook", text: "Continue with Facebook")
            }

            // Sign Up Prompt
            HStack {
                Text("Don’t have an account?")
                    .foregroundColor(.gray)
                Button(action: {}) {
                    Text("Sign up")
                        .fontWeight(.bold)
                        .foregroundColor(.blue)
                }
            }
            .padding(.top, 10)

            Spacer()
        }
        .padding()
    }
}

// Custom Button for Social Login
struct SocialLoginButton: View {
    let icon: String
    let text: String

    var body: some View {
        Button(action: {}) {
            HStack {
                Image(systemName: icon)
                Text(text)
            }
            .foregroundColor(.black)
            .frame(maxWidth: .infinity)
            .padding()
            .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
        }
        .padding(.horizontal)
    }
}

// Preview
struct LoginView_Previews: PreviewProvider {
    static var previews: some View {
        LoginView()
    }
}
✅ Features Implemented
Fixes the "ContentView not found" error by ensuring ContentView.swift exists.
Creates a beautiful login screen with:
Email and Password Inputs (with validation-ready fields).
Login Button styled with rounded corners.
"Forgot Password?" Link.
"Continue with Apple, Google, Facebook" Buttons.
"Sign Up" Link at the bottom.
🔥 Next Steps
Run the project in Xcode:
Press Command + B (Build).
Press Command + R (Run on Simulator).
If you get errors, make sure Campus_Navigator is selected as the target in Xcode.
This should now work perfectly! 🎯🚀 Let me know if you need any modifications. 😊







You said:
I need original google and Facebook logos for thisto add this 
ChatGPT said:
To use the original Google and Facebook logos in your SwiftUI login screen, follow these steps:

Step 1: Download Official Logos
You need the official Google and Facebook logos as image assets. Download them from:

Google logo → https://developers.google.com/identity/branding-guidelines
Facebook logo → https://en.facebookbrand.com/
Once downloaded, drag and drop these images into your Xcode project’s Assets.xcassets folder.

Name the Google logo: "google_logo"
Name the Facebook logo: "facebook_logo"
Step 2: Modify SocialLoginButton
Replace the SF Symbols icons (globe and facebook) with real images.

import SwiftUI

struct SocialLoginButton: View {
    let imageName: String
    let text: String

    var body: some View {
        Button(action: {}) {
            HStack {
                Image(imageName) // Load the actual logo
                    .resizable()
                    .frame(width: 20, height: 20) // Adjust size
                    .aspectRatio(contentMode: .fit)

                Text(text)
                    .foregroundColor(.black)
                    .font(.system(size: 16))
            }
            .frame(maxWidth: .infinity)
            .padding()
            .background(RoundedRectangle(cornerRadius: 10).stroke(Color.gray, lineWidth: 1))
        }
        .padding(.horizontal)
    }
}
Step 3: Update LoginView to Use Custom Logos
Now update your LoginView to use google_logo and facebook_logo.

VStack(spacing: 10) {
    SocialLoginButton(imageName: "applelogo", text: "Continue with Apple")
    SocialLoginButton(imageName: "google_logo", text: "Continue with Google")
    SocialLoginButton(imageName: "facebook_logo", text: "Continue with Facebook")
}
Step 4: Run the App
Build (Cmd + B) and Run (Cmd + R).
Your Google and Facebook login buttons will now show their official logos!
This will make your app look more professional. Let me know if you need any changes! 🚀😊







Unable to share conversation
Sharing conversations with user uploaded images is not yet supported




Search

Reason
