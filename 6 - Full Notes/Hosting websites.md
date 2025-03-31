2024-08-01 14:25

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Hosting websites

**What?**


**How?**





**Resources:**
Webhosts
- CloudFlare (Static Hosting, no SSR, CloudFlare Workers, KV Storage. Allows Teams of 5. Unlimited Bandwith + DDoS protection)
- Netlify (Static Hosting + SSR + Scheduled Functions + Netlify Edge Functions. No teams. 100 GB/m bandwidth )
- Vercel (Static Hosting + SSR + Serverless Functions + Edge Functions. No teams. 100 GB/m bandwidth)
- Firebase (Static Hosting + Realtime DB + FireStore + FireStorage)
- Render (Backend with ~15s cold reboot)
- GitHub Pages (Static Hosting, works best with Jekyll)
- Gatsby Cloud (Trash but use it if you actually use Gatsby)
- Azure (Free tier w/ credit card)
- DigitalOcean ($5 VMs, you can get some credit with GitHub edu pack)
- Oracle Cloud (Free tier w/ credit card but pretty shit)
- Deta (Deta Micros + CRON jobs, infinite Deta DB storage, 10 GB Deta Drive storage, but pretty shit)
API hosts
- Deta ( Serverless w/ 10s timeout- Python, Go, Node.js )
- Pythonanywhere ( Serverful, 1 free python project )
- CloudFlare ( Serverless w/ 10s timeout, node.js & cloudflare workers )
- Vercel ( Serverless w/ 10s timeout, cached responses, supports Go, Python, Node.js, Ruby )
- Netlify ( Serverless w/ 10s timeout, Node.js, Go )
- Firebase, Gatsby Cloud ( Serverless w/ 10s timeout, Node.js )
- Railway ( Serverful, most languages you can think of )
- Deno ( only supports deno projects, not sure if there's a timeout )
Databases hosts
- Deta Base (Unlimited but no locks, 16 digit numbers at max, and 8 MB limit for single record)
- Firebase (Very limited, but allows realtime)
- MongoDB (516 MB, 16 MB per document)
- SupaBase (Postgres under the hood, like Firestore, 516 MB)
- Cloudflare KV ( 1gb, limited read, writes, deletes, updates )
- PlanetScale ( 5 gb vitess (mysql), no window functions or CTE)
- Cockroach DB ( 5 gb Postgresql compatible )
- (Note: a lot of free options out there for Cassandra)
Pubsub / Realtime
- Pusher (pubsub channels, 200k msg)
- Ably (pubsub channels, 100k msg)
- Firebase (firestore or realtime db)


# References

