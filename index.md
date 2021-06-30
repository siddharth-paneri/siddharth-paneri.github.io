## Who is Siddharth?
[View On Github](http://github.com/siddharth-paneri)

With more than 9 years of industry experience in native iOS development, I enjoy all the aspects of development and have strong skills in design, architecture, UX standards, and DevOps for Mobile. 

I am equally at ease with the team dynamics and work culture of start-ups as well as enterprises and am well-versed with Agile ways of working and able to coach teams to be more efficient.

I stay on top of coding standards, automation testing, security issues, code complexity & vulnerabilities as they highly control the quality of our final product. 

I strongly believe in the idea of Q-OTIF (quality-on-time-in-full) which has been instrumental in the big successes of the various products I worked with.


### Too much to read? - Enjoy the output below

```
You get --- 

• iOS App.
• iPad App.
• watchOS App.
• macOS App.
• Jenkins CI/CD setup
• Automated build-test-release cycle
• Ensure quality and timely delivery
• Digital transformation
• Understanding gaps, SWOT and RISK
• Coach your teams to deliver quality on time in full.
```

### Wondoring how you got this output, try runing it in your machine :) 

```swift

/// Technologies that Sid can work on, independently or in a team.
enum Technology {
    case iOS
    case iPad
    case watchOS // exploring
    case macOS // exploring
    case tvOS // exploring
}

/// Final product types that you get when you invest in Sid.
enum FinalProductType {
    case all // all of the below
    case iOSApp // native
    case iPadApp // native
    case watchOSApp// natiive
    case macOSApp // native
    case tvOSApp // native, no experience
    case consulting // help you with something
    case devopsMobile // help you with your CI/CD for mobile
    
    var value: String {
        let grow = """

                • Digital transformation
                • Understanding gaps, SWOT and RISK
                • Coach your teams to deliver quality on time in full.
                """
        let iOS = """

                • iOS App.
                """
        let iPad = """

                • iPad App.
                """
        let watchOS = """

                • watchOS App.
                """
        let macOS = """

                • macOS App.
                """
        let devops = """

                • Jenkins CI/CD setup
                • Automated build-test-release cycle
                • Ensure quality and timely delivery
                """
        switch self {
        case .all:
            return iOS + iPad + watchOS + macOS + devops + grow
        case .iOSApp:
            return iOS
        case .iPadApp:
            return iPad
        case .watchOSApp:
            return watchOS
        case .macOSApp:
            return macOS
        case .tvOSApp:
            return "I can work on tvOS, but not an expert."
        case .devopsMobile:
            return devops
        case .consulting:
            return grow
        }
    }
}

/// The concrete Final product containing the deliverables, your return on investment
struct FinalProduct {
    let deliverables: [FinalProductType]
    init(_ deliverables: [FinalProductType]) {
        self.deliverables = deliverables
    }
    func receive() {
        print("You get --- ")
        deliverables.forEach { print("\($0.value)")}
    }
}

/// Contract that an Engineer must follow, to be an engineer ;)
protocol Engineer {
    var technologies: [Technology] {get set}
    
    init(_ technologies: [Technology])
    func  buildSomething() -> FinalProduct
}
extension Engineer {
    func buildSomething() -> FinalProduct{
        print("I promise I can build you something")
        return FinalProduct([.all])
    }
}
/// Mobile engineer, follows Engineer contract/rules
struct MobileEngineer: Engineer {
    var technologies: [Technology]
    var skills = [String]()
    
    init(_ technologies: [Technology]) {
        precondition(technologies.count > 0, "Dev with no tech! Who aaare yoou?")
        self.technologies = technologies
    }
}

extension MobileEngineer {
    func buildSomething() -> FinalProduct {
        return FinalProduct([.all])
    }
    func build_iOSApp() -> FinalProduct {
        return FinalProduct([.iOSApp])
    }
    func build_iPadApp() -> FinalProduct {
        return FinalProduct([.iPadApp])
    }
    func build_watchOSApp() -> FinalProduct {
        return FinalProduct([.watchOSApp])
    }
    func build_macOSApp() -> FinalProduct {
        return FinalProduct([.macOSApp])
    }}

var sid = MobileEngineer([.iOS, .iPad, .watchOS, .macOS])

let product = sid.buildSomething()
product.receive()

```
