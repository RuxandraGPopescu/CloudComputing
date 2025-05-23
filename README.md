Gestionarea cărților din biblioteca personală
								Popescu Ruxandra Georgiana
										1134
Link video https://youtu.be/GeUtDeOwWE8 
Link publicare https://cloud-computing-delta.vercel.app/ 
Link Github https://github.com/RuxandraGPopescu/CloudComputing
1.	Introducere
Această aplicație web este concepută pentru a gestiona colecția de cărți dintr-o bibliotecă personală. Utilizatorii au posibilitatea de a adăuga, edita, vizualiza și șterge cărți, fiecare având informații precum titlul, autorul și statusul (citită, necitită, în curs de citire). Interfața este simplă și intuitivă, dezvoltată cu ajutorul React și Next.js, iar datele sunt stocate și gestionate prin intermediul unui API.
2.	Descriere problemă
Oamenii care citesc frecvent se confruntă adesea cu dificultăți în a-și gestiona colecția de cărți, inclusiv titlurile citite sau cele pe care doresc să le citească. Fără un sistem organizat, este ușor să achiziționezi duplicate sau să uiți anumite titluri. Această aplicație abordează aceste probleme, oferind un sistem de management simplu și eficient.
Am utilizat două servicii în cloud, respectiv MongoDB și Vercel. 
Am ales MongoDB pentru a stoca datele aplicației mele sub formă de json. Astfel, sunt salvate toate cărțile introduse în aplicația mea.
![image](https://github.com/user-attachments/assets/6f02f6db-41a4-4f10-946a-d94cbb0356c5)

Vercel realizează hosting pentru aplicația web. Permite un deploy rapid și se sincronizează cu Github, actualizând aplicația automat.
4.	Descriere API
Aplicația folosește un API REST pentru gestionarea resurselor de tip “carte”. Acest API servește ca punct de comunicare între interfața client și baza de date. Fiecare operațiune se realizează printr-un apel HTTP către un endpoint specific, care manipulează datele în format JSON. 
-Listare cărți: acest endpoint returnează toate înregistrările din baza de date sub formă de listă de obiecte; este util pentru afișarea cărților într-un tabel sau într-o grilă de carduri în interfața vizuală. 
-Adăugare carte: se primește un obiect JSON ce conține detaliile cărții (titlu, autor, status); creează un nou document în colecția de cărți și returnează cartea adăugată, împreună cu un Id unic. 
-Editare carte: permite actualizarea informațiilor unei cărți existente, identificată prin Id; datele actualizate sunt transmise tot sub formă de JSON, iar răspunsul confirmă succesul actualizării.
-Ștergere carte: acest endpoint elimină o carte specifică din baza de date, identificată prin Id; se confirmă realizarea operației, nu returnează un obiect.
5.	Flux de date
•	Exemple de request/response 
Prin „get” am primit toate cărțile din bibliotecă alături de Id-ul lor:
 ![image](https://github.com/user-attachments/assets/6b2253a7-1018-4991-b729-e98e36039a23)

Prin “post” am adăugat o carte noua în biblioteca și am primit un id pentru aceasta.
![image](https://github.com/user-attachments/assets/4fbbb678-8456-4fa5-a0b4-941a4e799465)
 
Prin “put” am schimbat statusul cărții din “Not started” în “In Progress”:
![image](https://github.com/user-attachments/assets/88a4dbff-1b77-417a-bc3b-5f74d66dee6c)

Am realizat operația de ștergere folosind id-ul returnat la operația de adăugare.
![image](https://github.com/user-attachments/assets/a34f1d2b-183a-41ce-8b24-2cc273610979)

•	Metode HTTP
GET-folosit pentru a obține lista cărților
POST-se utilizează pentru a adăuga o carte nouă
PUT-este utilizat pentru a edita datele unei cărți existente
DELETE- folosit pentru a șterge o carte din biblioteca digitală
5.	Capturi ecran
Imediat ce se deschide aplicația se poate vedea biblioteca digitală:
![image](https://github.com/user-attachments/assets/49b7412a-c7fd-4d77-b89b-71ea6ff57360)
 
Aici am editat una dintre cărți pentru a schimba statusul acesteia. După completarea datelor am apăsat butonul Update care m-a dus la pagina principală pentru a vedea modificarea făcută.
Statusul inițial: 
 ![image](https://github.com/user-attachments/assets/621b644a-104d-45f1-b550-b5e3dc495b47)

Statusul după modificare:
 ![image](https://github.com/user-attachments/assets/b0959844-0e55-4e80-962b-4652697f958e)

Statusul nou apare în lista cu cărțile:
 ![image](https://github.com/user-attachments/assets/0d485e49-25b0-4416-8cfa-0ca18e3727dc)

Am realizat operația de adăugare a unei cărți noi. După completarea datelor, am apăsat butonul create pentru a adăuga cartea în lista. 
 ![image](https://github.com/user-attachments/assets/d55fdbcd-a9d9-4fb4-ba7a-3f65a726effb)
![image](https://github.com/user-attachments/assets/56e761e3-dc59-4e3d-82c8-63827b8ee997)

Se poate observa funcționalitatea butonului Delete, cartea fiind ștearsă din bibliotecă 
![image](https://github.com/user-attachments/assets/c9e91362-213a-441d-a383-2d143d799e54)

 
6.	Referințe
https://flowbite.com/docs/components/buttons/
https://cloud.mongodb.com/v2/6828b73044c1c11a7ba299d0#/overview
https://flowbite.com/docs/customize/colors/
https://flowbite.com/docs/components/spinner/
https://vercel.com/ruxandras-projects-258269fe
This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/pages/api-reference/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/pages/building-your-application/routing/api-routes) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.js`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/pages/building-your-application/routing/api-routes) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/pages/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn-pages-router) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/pages/building-your-application/deploying) for more details.
