<template>
  <section id="kapcsolat">
    <div
      class="kapcsolat"
      :style="{
        'background-image': `url(${require('../assets/images/kapcsolat.jpg')})`,
      }"
    >
      <div>
        <div class="kapcsolat_blur">
          <div class="container" style="padding-bottom: 100px">
            <h1 class="display-1 white" style="color: whitesmoke">
              Lépj velünk
            </h1>
            <h1 class="display-2 white" style="color: whitesmoke">
              kapcsolatba!
            </h1>

            <div class="row">
              <div class="col kapcsolat_box">
                <img
                  src="../assets/images/kapcsolat/phone.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">+36/70-339-4465</p>

                <img
                  src="../assets/images/kapcsolat/email.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">kokovon@kokovon.com</p>

                <img
                  src="../assets/images/kapcsolat/facebook.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">Kőkövön Vendégház</p>

                <img
                  src="../assets/images/kapcsolat/instagram.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">kokovon_vendeghaz</p>

                <img
                  src="../assets/images/kapcsolat/maps.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">
                  8230 Balatonfüred, Bajcsy-Zsilinszky u. 28.
                </p>

                <button
                  type="button"
                  class="btn btn-light"
                  data-toggle="modal"
                  data-target="#DataProtectionModal"
                >
                  Adatvédelmi nyilatkozat
                </button>

                <img src="../assets/images/szep_kartya.png" alt="Szep_kartya" />
              </div>

              <div class="col kapcsolat_box">
                <form @submit.prevent="sendContact">
                  <div class="col-6">
                    <div class="form-group">
                      <label for="inputName" style="color: whitesmoke"
                        >Neved:</label
                      >
                      <input
                        v-model="contact_name"
                        type="text"
                        class="form-control"
                        id="contactInputName"
                        placeholder="Név"
                        name="contact_name"
                        required
                      />
                    </div>

                    <div class="form-group">
                      <label for="inputEmail" style="color: whitesmoke"
                        >E-mail címed:</label
                      >
                      <input
                        v-model="contact_email"
                        type="email"
                        class="form-control"
                        id="contactInputEmail"
                        placeholder="E-mail"
                        name="contact_email"
                        required
                      />
                    </div>

                    <div class="form-group">
                      <label for="inputMessage" style="color: whitesmoke"
                        >Üzeneted:</label
                      >
                      <textarea
                        class="form-control"
                        id="contactInputMessage"
                        rows="3"
                        v-model="contact_message"
                        name="contact_message"
                        required
                      ></textarea>
                    </div>
                    <button
                      type="button kuldes submit"
                      class="btn btn-dark mt-4 btn-lg"
                    >
                      Küldés
                    </button>
                    <div
                      class="alert"
                      role="alert"
                      style="margin: 10px 0px"
                      id="contact_alert"
                    ></div>
                  </div>
                </form>
              </div>

              <div class="col kapcsolat_box">
                <img
                  src="../assets/images/kapcsolat/quote_top.png"
                  class="quote_top"
                  alt="..."
                />
                <p class="rolunk">Rólunk mondták</p>
                <p class="velemeny">
                  Csodás. Egyszerűen csodás. Béke van, romantika van, nyugalom
                  van, bicikli van, és csupa-csupa apró figyelmesség, kedvesség,
                  mindenhol. Nagyon szerettük!
                </p>
                <img
                  src="../assets/images/kapcsolat/quote_bottom.png"
                  class="quote_bottom"
                  alt="..."
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      class="modal fade"
      id="DataProtectionModal"
      tabindex="-1"
      role="dialog"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <button
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <b>Adatvédelmi tájékoztató</b><br /><br />

            A kokovon.com üzemeltetője ezúton tájékoztatja a honlap látogatóit a
            személyes adatok kezelése körében követett gyakorlatáról, az adatok
            védelme érdekében megtett szervezési és technikai intézkedéseiről,
            valamint a látogatók ezzel kapcsolatos jogairól, és azok
            érvényesítésének lehetőségeiről.

            <br /><br /><b>Adatkezelő neve, elérhetőségei </b><br /><br />

            Az adatkezelő megnevezése: Kőkövön Vendégház (a továbbiakban:
            Adatkezelő) <br />
            Képviselője: Medgyesy Bálint (2045 Törökbálint, Deák Ferenc u.
            37)<br />
            Az adatkezelő címe: 8230 Balatonfüred Bajcsy Zsilinszky utca 28.<br />
            Az adatkezelő e-mail címe: kokovon@kokovon.com<br />
            Az adatkezelő telefonszáma: 36205684724 <br /><br />

            <b
              >A honlapon végzett adatkezelések jogszabályi háttere, jogalapja,
              célja, a kezelt személyes adatok köre, valamint az adatkezelés
              időtartama
            </b>
            <br /><br />
            <b>A megrendeléssel és a számlázással kapcsolatos adatkezelés </b
            ><br />
            <b>Az adatkezelés jogszabályi háttere és jogalapja </b>
            <br /><br />
            Az adatkezelés hátterét az információs önrendelkezési jogról és az
            információszabadságról szóló 2011. évi CXII. törvény (Infotv.) és a
            számvitelről szóló 2000. évi C. törvény (Sztv.) rendelkezései
            jelentik. Az adatkezelés jogalapja az Infotv. 5. § (1) bekezdés a)
            pontjával összhangban az Ön hozzájárulása, valamint – hozzájárulása
            visszavonása esetén – az Infotv. 6 § (5) bekezdése a) pontja alapján
            az Adatkezelőt terhelő, Sztv-ben megfogalmazott jogi kötelezettség
            teljesítése.
            <br /><br />
            <b>Az adatkezelés célja: </b>
            <br /><br />
            A jogszabályoknak megfelelő számla kiállítása és a számviteli
            bizonylat-megőrzési kötelezettség teljesítése. Az Sztv. 169. §
            (1)-(2) bekezdése alapján a gazdasági társaságoknak a könyvviteli
            elszámolást közvetlenül és közvetetten alátámasztó számviteli
            bizonylatot meg kell őrizniük
            <br /><br />
            <b>A kezelt adatok köre: </b>
            <br /><br />
            Név, cím, e-mail cím, telefonszám. Cégek esetén adószám is
            <br /><br />
            Az adatkezelés időtartama:
            <br /><br />
            A kiállított számlákat az Sztv. 169. § (2) bekezdése alapján a
            számla kiállításától számított 8 évig meg kell őrizni. Tájékoztatjuk
            arról, hogy amennyiben a számla kiállításához adott hozzájárulását
            visszavonja, az Adatkezelő az Infotv. 6. § (5) bekezdés a) pontja
            alapján jogosult a számla kiállítása során megismert személyes
            adatait 8 évig megőrizni.
            <br /><br />

            <b>További adatkezelések</b> <br /><br />

            Amennyiben az Adatkezelő további adatkezelést kíván végezni, akkor
            előzetes tájékoztatást nyújt az adatkezelés lényeges körülményeiről
            (adatkezelés jogszabályi háttere és jogalapja, az adatkezelés célja,
            a kezelt adatok köre, az adatkezelés időtartama. Tájékoztatjuk Önt
            arról, hogy a hatóságok törvényi felhatalmazáson alapuló, írásbeli
            adatkéréseit az Adatkezelőnek teljesítenie kell. Az Adatkezelő az
            adattovábbításokról az Infotv. 15. § (2)-(3) bekezdésével
            összhangban nyilvántartást vezet (mely hatóságnak, milyen személyes
            adatot, milyen jogalapon, mikor továbbított az Adatkezelő), amelynek
            tartalmáról kérésére az Adatkezelő tájékoztatást nyújt, kivéve, ha a
            tájékoztatását törvény kizárja.
            <br /><br />
            <b
              >Adatfeldolgozó igénybevételéről és az adatkezeléshez kapcsolódó
              tevékenységükről
            </b>
            <br /><br />
            <b>A személyes adatok tárolása:</b>
            <br /><br />
            Kőkövön Vendégház (8230 Balatonfüred Bajcsy Zsilinszky utca 28.)
            képviselője Medgyesy Bálint (2045 Törökbálint, Deák Ferenc u. 37.)
            <br />Adószám:55141509-1-33<br />
            Adóazonosító: 8359112835<br /><br />

            Az Adatfeldolgozó az Adatkezelővel kötött írásbeli szerződés alapján
            közreműködik a számviteli bizonylatok könyvelésében. Ennek során az
            Adatfeldolgozó az érintett nevét és címét a számviteli
            nyilvántartáshoz szükséges mértékben, a Sztv. 169. § (2)
            bekezdésének megfelelő időtartamban kezeli, ezt követően
            haladéktalanul törli.
            <br /><br />
            <b>Adatbiztonsági intézkedések </b>
            <br /><br />
            Az Adatkezelő kijelenti, hogy megfelelő biztonsági intézkedéseket
            hozott annak érdekében, hogy a személyes adatok védje a jogosulatlan
            hozzáférés, megváltoztatás, továbbítás, nyilvánosságra hozatal,
            törlés vagy megsemmisítés, valamint a véletlen megsemmisülés és
            sérülés, továbbá az alkalmazott technika megváltozásából fakadó
            hozzáférhetetlenné válás ellen.
            <br /><br />
            <b>Az adatkezelés során Önt megillető jogok </b>
            <br /><br />
            Az adatkezelés időtartamán belül Önt megilleti: <br />
            <ul>
              <li>a tájékoztatáshoz való jog,</li>
              <li>az adatok helyesbítéshez való jog,</li>
              <li>az adatok törléséhez való jog,</li>
              <li>az adatok zárolásához való jog,</li>
              <li>a tiltakozás joga.</li>
            </ul>
            <br /><br />
            Ön az adatkezelés időtartamán belül tájékoztatást kérhet az
            Adatkezelőtől a személyes adatai kezeléséről. Az Adatkezelő a
            kérelem benyújtásától számított legrövidebb idő alatt, legfeljebb
            azonban 25 napon belül írásban, közérthető formában tájékoztatja Önt
            a kezelt adatokról, az adatkezelés céljáról, jogalapjáról,
            időtartamáról, továbbá – amennyiben az adatok továbbítására is sor
            került – arról, hogy kik és milyen célból kapják vagy kapták meg az
            adatokat. Ön az adatkezelés időtartamán belül kérheti, hogy az
            Adatkezelő a személyes adatait helyesbítse. A kérésének az
            Adatkezelő legkésőbb 15 napon belül eleget tesz. Önnek lehetősége
            van a személyes adatainak törlését kérni, amelynek az Adatkezelő
            legkésőbb 15 napon belül eleget tesz. A törlés joga nem terjed ki
            arra, ha az Adatkezelőt törvény kötelezi az adatok további
            tárolására, illetve arra az esetre, sem ha az Infotv. 6. § (5)
            bekezdésével összhangban az Adatkezelő jogosult a személyes adatok
            további kezelésére (így például a számlázással összefüggésben).
            <br />Ön kérheti, hogy az Adatkezelő zárolja a személyes adatot, ha
            az adatok végleges törlés sértené az érintett jogos érdekeit. Az így
            zárolt személyes adat kizárólag addig kezelhető, ameddig fennáll az
            az a cél, amely a személyes adat törlését kizárta. <br />Ön
            tiltakozhat személyes adatának kezelése ellen, <br />
            <ul>
              <li>
                ha a személyes adatok kezelése vagy továbbítása kizárólag az
                Adatkezelőre vonatkozó jogi kötelezettség teljesítéséhez vagy az
                Adatkezelő, adatátvevő vagy harmadik személy jogos érdekének
                érvényesítéséhez szükséges, kivéve kötelező adatkezelés esetén
                és az Infotv. 6. § (5) bekezdésében foglalt esetben;
              </li>
              <li>
                ha a személyes adat felhasználása vagy továbbítása – az Ön
                hozzájárulása nélkül – közvetlen üzletszerzés,
                közvélemény-kutatás vagy tudományos kutatás céljára történik. Az
                Adatkezelő a tiltakozást a kérelem benyújtásától számított
                legrövidebb időn belül, de legfeljebb 15 napon belül
                megvizsgálja, annak megalapozottsága kérdésében döntést hoz, és
                döntéséről Önt írásban tájékoztatja. Ha az adatkezelő az
                érintett helyesbítés, zárolás vagy törlés iránti kérelmét nem
                teljesíti, a kérelem kézhezvételét követő 25 napon belül írásban
                vagy az érintett hozzájárulásával elektronikus úton közli a
                helyesbítés, zárolás vagy törlés iránti kérelem elutasításának
                ténybeli és jogi indokait.
              </li>
            </ul>

            <br /><br />
            <b>Jogorvoslati lehetőségek </b>
            <br /><br />
            Amennyiben Ön szerint az Adatkezelő megsértette valamely, az
            adatkezelésre vonatkozó törvényi rendelkezést, vagy nem teljesítette
            valamely kérelmét, akkor vélelmezett jogellenes adatkezelés
            megszüntetése érdekében a Nemzeti Adatvédelmi és Információszabadság
            Hatóság vizsgálati eljárását kezdeményezheti (levelezési cím: 1530
            Budapest, Pf.: 5., e-mail: ugyfelszolgalat@naih.hu). Tájékoztatjuk
            emellett arról is, hogy az adatkezelésre vonatkozó törvényi
            rendelkezések megsértése esetén, vagy ha az Adatkezelő nem
            teljesítette valamely kérelmét, akkor az Adatkezelővel szemben
            bírósághoz fordulhat.
            <br /><br />
            <b>Adatkezelési tájékoztató módosítása </b>
            <br /><br />
            Az Adatkezelő fenntartja a jogot, hogy jelen adatkezelési
            tájékoztatót módosítsa. A honlap módosítás hatálybalépését követő
            használatával elfogadja a módosított adatkezelési tájékoztatót.
          </div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary"
              data-dismiss="modal"
            >
              Bezárás
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  name: "Kapcsolat",

  data() {
    return {
      contact_name: undefined,
      contact_email: undefined,
      contact_message: undefined,
    };
  },
  methods: {
    sendContact(e) {
      try {
        emailjs.sendForm(
          "service_7l0rp2n",
          "template_4vn6c3f",
          e.target,
          "user_2fTzZBeA9lR7RMZjUkzge",
          {
            contact_name: this.contact_name,
            contact_email: this.contact_email,
            contact_message: this.contact_message,
          }
        );
        document
          .getElementById("contact_alert")
          .classList.remove("alert-danger");
        document.getElementById("contact_alert").classList.add("alert-success");
        document.getElementById("contact_alert").innerHTML = "Üzenet elküldve!";
        // Reset form field
        this.contact_name = undefined;
        this.contact_email = undefined;
        this.contact_message = undefined;
      } catch (error) {
        document.getElementById("contact_alert").classList.add("alert-danger");
        document.getElementById("contact_alert").innerHTML =
          "A küldés sikertelen, további informácóért hívd az alábbi telefonszámot: +36703394465";
      }
    },
  },
};
</script>