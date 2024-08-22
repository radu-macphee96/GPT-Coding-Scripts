# Star Trek coding script (1)
"Exolinguistic Comprehensive Translation Matrix" - Star Trek =^=

CODE BELOW (❗️but not yet ready for pasting to swift playgrounds or xcode❗️- only for visual analysis)

import SwiftUI
import PlaygroundSupport

struct TranslationMatrixView: View {
    let phrases: [String]
    let translations: [String]
    
    var body: some View {
        VStack(spacing: 20) {
            Text("Exolinguistic Comprehensive Translation Matrix")
                .font(.title)
                .padding(.top, 20)
            
            ForEach(0..<phrases.count) { index in
                HStack {
                    Text(phrases[index])
                        .font(.body)
                        .frame(width: 250, alignment: .leading)
                        .padding(.leading, 30)
                    Spacer()
                    Text(translations[index])
                        .font(.body)
                        .frame(width: 250, alignment: .leading)
                        .padding(.trailing, 30)
                }
            }
            
            Spacer()
        }
    }
}

struct ContentView: View {
    let vulcanPhrases = [
        "Live long and prosper",
        "Peace and long life",
        "Logic is the beginning of wisdom, not the end",
        "I have been and always shall be your friend",
        "The needs of the many outweigh the needs of the few",
        "May you live long and prosper"
    ]
    
    let vulcanTranslations = [
        "Dif-tor heh smusma",
        "T'hy'la",
        "Kup-veh-tor t'kal-in-jei, t'kal-in-ahr-kei",
        "Taluhk nash-veh k'dular",
        "T'hy'la, kae tricatra, kae'shya",
        "Dif-tor heh smusma"
    ]
    
    let romulanPhrases = [
        "Strength and honor",
        "Freedom and unity",
        "Victory is life"
    ]
    
    let romulanTranslations = [
        "Khnai rhae n'var",
        "Vre'lan tr'daru",
        "S'taenok k'v'la"
    ]
    
    let klingonPhrases = [
        "Today is a good day to die",
        "Honor and glory",
        "Klingons never retreat"
    ]
    
    let klingonTranslations = [
        "Heghlu'meH QaQ jajvam",
        "batlh je",
        "tlhIngan maH ghaH reH"
    ]
    
    var body: some View {
        NavigationView {
            TranslationMatrixView(phrases: vulcanPhrases + romulanPhrases + klingonPhrases,
                                  translations: vulcanTranslations + romulanTranslations + klingonTranslations)
                .navigationBarTitle("Exolinguistic Translator")
        }
    }
}

PlaygroundPage.current.setLiveView(ContentView())
PlaygroundPage.current.needsIndefiniteExecution = true
