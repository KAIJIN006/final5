StaySwift - Waiting List Confirmation Update

Files:
- app.py: Flask application with waiting-list confirmation improvements
- requirements.txt: Python dependencies
- static/rooms/: Standard, Deluxe, and Suite room images

Waiting-list behavior:
1. When a reservation is cancelled, StaySwift creates offers for matching waiting-list guests and attempts to email them.
2. Guests can also see an available offer directly on their Dashboard under "My waiting-list requests" using the "Review & Confirm" button. This works even if an email is not delivered.
3. Opening the offer page only displays the details. The guest must press "Confirm Reservation" to reserve the room.
4. The first successful confirmation gets the room. Other offers for the same room and overlapping dates are marked taken.
5. After confirmation, the waiting-list request displays as confirmed and the booking appears under "My reservations".
6. If a room became available before this update was deployed, the Dashboard checks existing waiting-list requests and creates an offer when a matching room is currently free.

Deployment:
- Replace the existing app.py in the GitHub repository with this app.py.
- Upload/keep the static/rooms folder and its three JPG files.
- Keep requirements.txt and existing Render environment variables unchanged.
- Commit changes and wait for Render to deploy.

Email sending still requires a valid RESEND_API_KEY and an authorized sender domain for sending to arbitrary customer email addresses. Dashboard confirmation works independently of email delivery.

School-project prototype note: review authentication, password storage, CSRF protection, and database persistence before any real-world production use.
